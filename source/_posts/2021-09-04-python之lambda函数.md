---
title: python之lambda函数
date: 2021-09-04 14:49:55
tags: [python, lambda]
---



## lambda函数

### 特性：

- lambda函数是匿名的：所谓匿名函数，通俗地说就是没有名字的函数。lambda函数没有名字。
- lambda函数有输入和输出：输入是传入到参数列表argument_list的值，输出是根据表达式expression计算得到的值。
- lambda函数一般功能简单：单行expression决定了lambda函数不可能完成复杂的逻辑，只能完成非常简单的功能。由于其实现的功能一目了然，甚至不需要专门的名字来说明。

### 用法：

- 将lambda函数赋值给一个变量，通过这个变量间接调用该lambda函数。
- 将lambda函数赋值给其他函数，从而将其他函数用该lambda函数替换。
- 将lambda函数作为其他函数的返回值，返回给调用者。
- 将lambda函数作为参数传递给其他函数。
