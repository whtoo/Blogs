---
title: 基于sodium的FRP解析
date: 2021-04-10 09:14:12
tags:
---

## 前言
为什么要写这篇日志？因为，我觉得有必要将这个问题（`FRP`）整理为一个有完整体系结构的*知识集*。

基于此，日志的格式和内容将是非常**个人化**的。因为，它主要是为了解决我自己的*知识管理*和*技术总结*而

形成的日志。

## 全局概览

### 类层次关系
{% asset_image class-graph.png "类层次结构"%}

### 与Rx的大致对应（不准确）
| 类名 | rx.js| 说明 |
| - | - | - |
| Cell | Rx.BehaviourSubject | 表示被观察的会变化的值的容器(cache line of data) |
| Lazy\<A\> | - | 对值类型A进行thunk的容器 |
| Listener  | -  | 监听函数容器 |
| Stream\<A\> | Rx.Observable | 值的变化瞬时传递管道 |
| Transaction\<A\> | - | Emitter的容器(closure simulator) |

### 模拟场景说明








