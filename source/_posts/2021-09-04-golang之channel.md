---
title: golang之channel
date: 2021-09-04 14:51:39
tags: [golang, channel]
---



## Channel

### 简介

如果在程序中启用了多个goroutine，那么这些groutine直接的通信就用channel来实现，go提供了一个channel（管道）数据类型，可以解决协程之间的通信问题，channel的本质是一个队列，遵循先进先出规则（FIFO），内部实现了同步，确保并发安全

### Channel的语法

channel在创建时，可以设置一个可选参数：缓冲区容量

#### 创建有缓冲channel：

```
make(chan int, 10)，// 创建 一个长度为10的channel
```

#### 创建无缓冲channel：

```
make(chan int)
```

channel中的类型可以为任意类型

### 读写数据

从管道中读取，或者向管道中写入数据，使用运算符：<-

```
Ch := make(chan int)

Ch <- 10 //写入数据

Num := <- chan //读取数据
```

### 无缓冲channel

无缓冲的channel是阻塞读写的，必须写端与读端同时存在

无缓冲通道的收发操作必须在两个不同的goroutine间进行，因为通道的数据在没有接收方处理时，数据发送方会持续阻塞，所以通道的接受必定在另一个goroutine中进行
如果不按照规则使用：则会引起经典的golang错误：fatal error: all  goroutines are asleep - deadlock!

有缓存的channel是非阻塞的，但是写满缓冲长度后，也会阻塞写入

### 无缓冲通道和有缓冲通道

#### 无缓冲

- 通道容量为0， 即cap(ch) = 0
- 通道的个数为0， 即len(ch) = 0
- 可以让读，写两端具备并发同步的能力

#### 有缓冲

- 在make创建的时候设置非0的容量值
- 通道的个数为当前实际存储的数据个数
- 缓冲据具备数据存储的能力，到达存储上限后才会阻塞，相当于具备异步能力
- 有缓冲channel的阻塞产生条件：

带缓冲通道被填满时，尝试发送数据就会发生阻塞

带缓冲通道为空时，尝试接收数据会发生阻塞

