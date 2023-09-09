---
layout: post 
title: Well ground Java Developer
category: Notes
---
## Chapter 1 Introduction to modern Java

### Java 语言与平台

提起Java这个词，很多人第一印象都是Java语言。Java语言在从出生开始到现在这30年里一直叱咤风云。但是在现代意义上讲，Java代表的已经不局限于Java语言了，而是Language + Platform。大体上讲，Java这个商标由Oracle拥有并管理。Oracle负责Java SE的开发，根据Java SE官网，Java SE 19的标准分为两部分：

* The Java Language Specification, Java SE 19 Edition

    Preview feature: Pattern Matching for switch； Record Patterns
* The Java Virtual Machine Specification, Java SE 19 Edition

其中 The Java Language指的就是那门原教旨面向对象的编程语言，而Java Virtual Machine就是Java程序员面试需要背诵但是从来都用不上的JVM。实际上JVM的官方实现已经没有任何和Java语言相关的字眼，对于JVM来说Java语言和其他任何一个可以编译为Bytecode的语言（Kotlin或Scala）一样。

### Java 发布模型

从2021年开始，Java每两年一个LTS，半年一个STS（看起来像是被别的语言刺激了）。
值得注意的是，JDK中有一些独立的OpenJDK project可能贯穿多个JDK的生命周期，每个project做的事情都不一样。比如Project Loom致力于在Java中实现协程，而Project Amber致力于让程序员少写代码。

## Chapter 13 Testing Fundamentals

### 13.1 如何测试？

软件的测试大致可以分为：

* 单元测试
* 集成测试
* 端到端测试

他们之间的关系可以用一个金字塔来表示：

![pasad](/assets/img/pyramid.png "the pyramin")

**单元测试：** 单元测试构成了整个金字塔的最底部。每个单元测试之间的隔离性最强，运行速度最快，所覆盖的内容也最单一。理想状态下，单个单元测试应该只测试单个功能。这里的单个功能指的是：自己的与外部依赖无关的逻辑。当所测试的逻辑有外部依赖时，如使用了数据库调用或者RPC，外部依赖返回的结果应该使用Mock的理想结果，这个叫做test double。

**集成测试：** 集成测试和单元测试之间的关系有时是模糊的。但仍然可以确定的是：集成测试只测试整个系统的一部分，另外仍有一部分依赖是被Mock的。比如：一个测试只测试某个后端服务的一个借口，这个后端服务中使用真实的数据库和RPC连接，而假定前端部分是完美的。

**端到端测试：** 端到端测试是最直观的测试，就是假定自己是用户，测试整个系统的输出是否与自己所期望的相匹配。

## 13.2 测试驱动开发
