---
title: CSS3实践研究
date: 2021-04-23 11:45:33
tags:
---
# 拥抱流布局

1. 布局(layout)
    1. 响应式与媒体查询
    2. flexible box layout
    3. grid layout
2. 视觉表现
    1. corner、shadow、progressive
    2. transform
    3. fitler
    4. animatation

## 术语
``` CSS
.track-item {
    width: 480px;
    height : 640px;
    color : 'red';
}
```

1. 属性
`height`和`color`就是属性。


2. 值

| 类型 | 说明|
| -   |   - |
| int | 属于number|
| number | 浮点数 |
| percent | 50% |
| length | 99px |
| color  | #999 |

3. 关键字
`transparent`

4. 变量
`currentColor`

5. 长度单位

`<number> + 长度单位 = <length>`

6. 功能符
`rgba(0,0,0,5)`
`url('css-world.png')`

7. 属性值
`1px solid rgb(0,0,0)` <- `值+关键字+功能符`

8. 声明
`color : transparent`

9. 声明块
```CSS
{
    width : 10%,
    color : 'red'
}
```

10. 规则或规则集
```CSS
.track-item {
    width: 480px;
    height : 640px;
    color : 'red';
}
```

11. 选择器

| 选择器 | 符号 | 优先级 |
| - | - | - |
| 类选择器 | '.' | 默认 |
| ID选择器 | '#' | 高  |
| 属性选择器 | '[]' |  |
| 伪类选择器 | ':' |  |
| 伪元素选择器 | '::before' | |