---
layout: post  
title: EntityFramework在重构项目中的使用 （未完）     
category: 技术    
tags: 项目      
keywords:        
description:       
---  

##  一、缘起  
+ 导师一直想做个目前版本的重构。时间点大概是
	+ 2016-12-14开始拉我进项目组，开始讨论一些模块的划分，以及图的制作。
	+ 2017-01-11

##  二、内容
###  （1）Data Layer
+ 最开始的`Model`导师2017-01月想让我写，我之前原来没啥概念。
	+ 业务上没啥概念
	+ 技术上没怎么接触过，也不知道如何落地。
+ 2017-03月做完`Project`模块的全流程后，要开始补充外键以及其它项目模块。

###  （2）Mapping in Data.SqlServer Layer
+ 属性映射
	+ 配置主键 
		+ `HasKey(b => b.ID); `
		+ `Property(b => b.ID).HasDatabaseGeneratedOption(DatabaseGeneratedOption.Identity); //主键自增`
	+ 配置复合主键
	+ 配置外键
	+ 配置组合外键
		+ o
	+ 配置DataType
		+ `String`->`nvarchar`
		+ `int`->`int`
		+ `Byte[]`->`varbinary`  
		+ `Boolean`->`bit` //不允许为空
		+ `Datetime`->
	+ 配置string类型的长度和必填/可选
		+ `.Property(p => p.Name).HasColumnType("varchar")`
	+ GUID的Id 
		+ `Property(p => p.Id).HasDatabaseGeneratedOption(DatabaseGeneratedOption.Identity)`
		+ *非GUID的话，无法没有初值会不会ID会从2开始？*
	+ 更改数据库中的model的默认字段名
		+ `Property(p => p.Name).HasColumnName("DBName");` 
	+ 时间戳 
		+  `Property(p => p.TimeStamp).IsRowVersion();`
		+   `Property(p => p.TimeStamp).IsRowVersion().IsFixedLength();` //将列配置为固定长度
		+ 在Model层的定义 `public Byte[] TimeStamp { get; set; }` 
+ [类型映射](http://www.jianshu.com/p/4b043b3a7df5)
	+ 映射TPH
	+ 映射TPT
	+ 映射TPC
+ 配置关系
	+ 配置（1-0...1）关系 
	+ 配置（1-1）关系
	+ 配置（1-n）关系
		+ `HasMany(b => b.Projects)
                .WithOptional(p => p.Base)
                .HasForeignKey(p => p.BaseId)
                .WillCascadeOnDelete(false);`
	+ 配置（n-n）关系
+ 配置导航属性
+ 启用级联删除
+ 忽略列/表映射 *可以通过计算获得，并不需要记录在数据库中*
	+ `Ignore(b => b.value);`
	+ `Ignore(Person); // 我没具体用过` 

###  （3）Context in Data.SqlServer Layer
+ Context.cs
+ [Code First Database Connection](http://blog.163.com/m13864039250_1/blog/static/21386524820152885817287/)
+ [Code First Migrations](http://blog.163.com/m13864039250_1/blog/static/2138652482015289109327/) 

###  （4）项目中遇到的问题

##  三、更进一步思考
+ （1）如何对一个.mdf进行面向对象的分析，除了EF和建模工具，并且用了这些工具，如何深入？
+ （2）怎么算学好了数据库设计？

##  四、参考
+ [EF Code First 学习笔记：约定配置](http://www.cnblogs.com/Gyoung/archive/2013/01/17/2864150.html)
+ [Code First约定-Fluent API配置](http://blog.163.com/m13864039250_1/blog/static/2138652482015283397609/)
+ [entityframeworktutorial](http://www.entityframeworktutorial.net/code-first/inheritance-strategy-in-code-first.aspx)
+ [FluentAPI配置](http://www.cnblogs.com/cuijl/p/6737815.html)
+ [Entity Framewokr一个博客系列](http://www.cnblogs.com/dudu/tag/Entity%20Framework/)
##  五、复盘&思考

