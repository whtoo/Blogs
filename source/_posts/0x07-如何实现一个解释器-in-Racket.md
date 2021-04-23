---
title: 0x07.如何实现一个解释器 in Racket
date: 2021-04-21 19:12:01
tags:
---
# 可变量的结构与表示

## 赋值
```Java
    float a = 0.1;
    Person p1 = new Person("Jackson");
    p1.salary = 100000;
```

### 如何实现上述语义呢？

#### 盒子里的变量

`In Racket` : substitution-value
```Racket
#lang typed-plai 

(define-type ExprC)
    ...
    [BoxC (val : Value)]
)
```

`In Java `: ref-replacement
``` Java
class Box<T> {
      private T the_value;
      Box(T v) {
          this.the_value = v;
      }
      T get() {
          return the_value;
      }
      void set(T v) {
          the_value = v;
      }
}
```

