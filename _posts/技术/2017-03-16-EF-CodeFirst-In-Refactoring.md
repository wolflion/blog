---
layout: post  
title: EntityFramework在重构项目中的使用 （未完）  
category: 技术   
tags: 项目      
keywords:      
description:    
---  

##  缘起
+ 导师一直想做个目前版本的重构。时间点大概是
	+ 2016-12-14开始拉我进项目组，开始讨论一些模块的划分，以及图的制作。
	+ 2017-01-11

##  内容
###  Data Layer
+ 最开始的`Model`导师2017-01月想让我写，我之前原来没啥概念。
	+ 业务上没啥概念
	+ 技术上没怎么接触过，也不知道如何落地。
+ 2017-03月做完`Project`模块的全流程后，要开始补充外键以及其它项目模块。

###  Data.SqlServer Layer
+ 属性映射
	+ 配置主键 `HasKey(b => b.ID); `
	+ 时间戳  `Property(p => p.TimeStamp).IsRowVersion();` 
		+ 在Model层的定义 `public Byte[] TimeStamp { get; set; }` 
+ 忽略列/表映射 *可以通过计算获得，并不需要记录在数据库中*
	+ `Ignore(b => b.value);`
	+ `Ignore(b => b.value);` 

##  更进一步思考

##  参考
+ [EF Code First 学习笔记：约定配置](http://www.cnblogs.com/Gyoung/archive/2013/01/17/2864150.html)
+ [Code First约定-Fluent API配置](http://blog.163.com/m13864039250_1/blog/static/2138652482015283397609/)

##  复盘&想法

