---
title: FRP的总结
date: 2021-04-10 09:22:48
tags:
- Reactive
- FRP
---

## 前言
我本来是想先写完上一篇[《基于sodium的FRP解析》](基于sodium的FRP解析.md)，再来编写这篇文章。但是，经过我的debug和trace，以及我之前使用`reactivecocoa`和`bacon.js`的经验。我决定还是先写本文来建立*FRP*的基本概念框架和基础实现路线图。毕竟，我的目的是让我自己掌握建立FRP系统的基本
概念和技术，有了这些基础就能定制化开发我需要的框架。


## 全局鸟瞰

- [ ] 增加subscriber、observable、subscription、stream等的概念图。
- [ ] 给出所有关键概念对应的实体的接口设计，以及职责描述
- [ ] 以rx.js为例给出关键实体的数据流分析

## 简化实现

### 实体-概念对应关系

### 实体与接口

### 是否引入事务性机制（inspired by sodium)

### 关键实现代码剖析

## 用例

我先用rx.js实验，然后使用我的实现去逐步替换。

### 坦克大战（[项目地址](https://github.com/whtoo/JSTankGame.git)）

