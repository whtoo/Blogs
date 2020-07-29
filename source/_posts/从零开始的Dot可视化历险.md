---
layout: photo
title: 从零开始的Dot可视化历险
date: 2020-07-29 14:13:53
tags:
- DOT
- Visualization
- Tutorial
---
## 1. 基本使用实例

### 1.1 一个C程序的内部调用图

{% asset_image demo.png "关于C调用程序的图示" %}
`如图1.1.a 所示`
{% include_code lang:dot demo.dot %}
******
{% asset_image demo_enhace.png "关于C调用程序的图示" %}
`如图1.1.b 所示`
{% include_code lang:dot demo_enhance.dot %}

## 2. 从基本结构开始探险

### 2.1 Node

{% asset_image demo_main_node.png "main node"%}
`如图 2.1.a 所示`

{% codeblock lang:dot %}
diagraph G {
    main [label="我是一个节点,名字叫做main"]
}
{% endcodeblock %}