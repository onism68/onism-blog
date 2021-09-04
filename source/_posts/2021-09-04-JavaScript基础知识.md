---
title: JavaScript基础知识
date: 2021-09-04 14:35:52
tags: [JavaScript, 基础知识]
---



## 模板字符串

模板字符串提供了另一种做字符串组合的方法。

```
const user = 'world';

console.log(`hello ${user}`); // hello world
```



## 默认参数

```
function log1(a = 1) {
	console.log(a);
}

log1(); // 1
```



## 箭头函数

函数的快捷写法，不需要通过 function关键字创建函数，并且还可以省略 return 关键字。同时，箭头函数还会继承当前上下文的 this 关键字。

```
[1, 2, 3].map(x => x + 1); // [2, 3, 4]
```



## ES6对象和数组

### 析构赋值

析构赋值让我们从 Object 或 Array  里取部分数据存为变量。

```
// 对象

const user = { name: 'zhang', age: 2 };

const { name, age } = user;

console.log(`${name} : ${age}`); // zhang: 2
```

### Spread Operator

Spread Operator 即 3 个点      ...，有几种不同的使用方法。

1. 用于组装数组
2. 也可用于获取数组的部分项
3. 还可以收集函数参数为数组
4. 代替apply
5. 对于 Object 而言，用于组合成新的 Object       。(ES2017 stage-2 proposal)

## Promises

Promise 用于更优雅地处理异步请求。比如发起异步请求

## Generators

Generator 返回的是迭代器，通过 yield      关键字实现暂停功能。
