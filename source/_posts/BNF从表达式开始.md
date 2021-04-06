---
title: BNF从表达式开始
date: 2021-03-12 10:41:14
tags:
---

[TOC]

# 表达式--BNF的起点
## 从算术计算说起
```
expr ->   expr + expr 
        | expr * expr
        | NUM;

NUM -> INT | FLOAT;
FLOAT -> INT '.' INT;
INT -> [0-9] | [1-9][0-9]+;
```
## 拆解算术表达式
``` expr -> expr + expr ```

## 合起来看
## 

