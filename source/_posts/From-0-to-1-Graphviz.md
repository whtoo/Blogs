---
layout: photo
title: 'From 0 to X: Hexo -- 0x01'
date: 2020-07-29 21:33:54
tags:
- Hexo
- Tag Plugins
- Graphviz
categories:
- 从零开始的Hexo探险🧶
---
## 0%: 从0开始的Hexo流程图探险

## 15%: Graphviz?Dot?这都是什么🧎‍♀️?

``` dot
digraph demo4 {
	label=<<B>Graphviz基本组成结构</B>>;

    labelloc=t;			// 标题位置
    bgcolor=white;	// 背景透明
    
    node[shape=box];		// 结点形状为方形
    //edge[style=bold];
    
    // 独立出现的为结点或属性声明, 中括号前为结点名称
    graphviz[label="Graphviz"];
    
    subgraph{
        layout[label="Layouts"];
        script[label="Script Files"];
        api[label="APIs"];
        rank=same;
    }
    
    graphviz -> layout;
    graphviz -> script;
    graphviz -> api;
    
    // 设置子图
    api -> 
    subgraph{
	    layout_etc[label="......"];
    }
    
    script ->
    subgraph{
        element[label="Elements"];
        attribute[label="Attributes"];
        rank=same;
    }
    
    layout ->
    subgraph{
        layout_dot[label="dot"];
        layout_neato[label="neato"];
    }
    
    element ->
    subgraph{
        ele_graph[label="Graph"];
        ele_node[label="Node"];
        ele_edge[label="Edge"];
    }
}
```

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

First Term
: This is the definition of the first term.

Second Term
: This is one definition of the second term.
: This is another definition of the second term.