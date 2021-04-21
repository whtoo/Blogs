---
title: 如何实现一个解释器 in Racket
date: 2021-04-21 09:55:28
tags:
---

## 前言
本文是`6. From Substitution to Environments`的实验记录。

## 计划
- [x] Define a environment
- [x] Implement lookup in environment

## codes
1. Define a environment as list.
```Racket
(define-type Binding
  [bind (name : symbol) (val : number)])
(define-type-alias Env (listof Binding))
```
2. Implement lookup in environment
```Racket
; DONE : Define lookup
(define (lookup [for : symbol] [env : Env]) : number
  (cond
    [(empty? env) (error 'lookup "name not found")]
    [else (cond
            [(symbol=? for (bind-name (first env)))
             (bind-val (first env))]
            [else (lookup for (rest env))])]))
```