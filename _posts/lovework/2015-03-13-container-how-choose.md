---
layout: post 
title: C# 集合选择
category: 技术
tags: C#
keywords: C#，集合选择，容器选择
description: 关于如何选择合适的容器进行编码
---

C# 集合选择
----------
数据结构指相互之间存在一个特定关系的元素集合。
线性集合就是指元素具有一个特定前驱和后继的数据结构。
非线性集合是指元素具有多个前驱或者后继的数据结构。

而C#的集合也可以通过此来进行区分看下图

![Continary](http://7x2xd3.com1.z0.glb.clouddn.com/AllDataContinary.png)

线性集合按存储方式，又分为直接存储和顺序存储。
直接存储是指：该类型集合的数据元素可以直接通过下标来访问。C#中有Array,List,String
和struct.优点是：取和在末尾存放数据都是非常高效的。但是缺点是：向集合中间插入元素，
非常低效。因为它需要给插入的元素腾出位置，并且所有它后面的元素都要往后移动一位。

顺序存储：一般大小都可以动态分配。它不能通过索引进行查找，但是可以通过地址进查询。
但是效率非常低。为了找到某个元素，它必须遍历所有元素，知道找到想找到的元素为止。
所以线性表的优点是插入和删除效率高，而缺点是查找的效率相对低一些。
队列Queue<T>遵循先入先出的原则，在集合末尾添加，在集合其实删除。
Stack<T>遵循的是后入先出原则。在集合末尾添加，在集合末尾删除。

为了选择你需要的集合，你必须要考虑你在集合上需要使用的操作。
数组是最简单的也是一般情况最快的集合。也是我们最常用的一个集合。
如果准备存储单一次序的对象，你也应该使用数组。
ArrayList 类是在数组上的一个高度抽象类。当你不清楚你的集合具体有多大时，ArrayList类
要比数组好很多。
队列和栈类都在System.Array类上提供了特殊的接口。所以动态分配内存，开销也非常大。
于是，在初始化时最好给定集合的容量大小。这样才能避免移动和拷贝元素的性能损失。
队列的默认大小是32，栈的默认大小是10.

垃圾回收的高效，是的list结构在实际使用是占用时间最小的。如果你因为希望经常添加和删除里面的元素而
选择了列表，那么使用null引用的字典。简单的存储关键字，你就可以使用listDictionary类。
而且它用键值对应方式实现了单向链表。这些集合和它的一些相关操作都在System.Collections.Specialized名字空间里。


