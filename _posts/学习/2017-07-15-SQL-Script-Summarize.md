---   
layout: post    
title: SQLScript整理            
category: 学习            
tags: 总结        
keywords:      
description:     
---  

##  缘起
+ 以前也整理过，感觉那时候那时候都是增、删、改、查、相关的，也没写视图啥的，现在有了应用场景，好好整理一下。

##  内容

###  查询
+ 使用LIKE及通配符
+ Order By排序
	+ 强制性地将输出按照一个特定值来排序
		+ `select au_lname,au_fname from authors order by au_lname`也可以用数字,只要数字和select里一致，比如`order by 1`
	+ 通过未出现在select列表中的列排序
		+ `select au_lname,au_fname from authors order by city`
+ Group By求子集合
+ Having从结果集中挑选行
+ 正确理解WHERE、GROUP BY和HAVING子句的执行顺序
+ 连接
	+ `SELECT t.*, pub_name,AVG(price) FROM titles t, publishers p WHERE t.pub_id = p.pub_id ` *得记住要用简写*
+ 子查询
	+ 带有IN的子查询
+ UNION
+ INTO
	+ `SELECT DISTINCT type INTO type_lookup FROM tiles`用于将结果创建到另一条表里，如果是临时表的话，在表名前加（#或者##）。
+ tips
	+ 除非必要，否则**不要使用DISTINCT**。*它会使服务器执行额外的分类和处理，将导致检索时间加长。*
	+ **不推荐在任何类型的程序中都使用`select *`**，因为*它会导致不可预见的程序行为或导致应用程序失败。*
	+ `select into`与`intsert into`前者是复制表，后者是拷贝表。


##  参考与收获
###  参考
+ 1、[SQL常见面试题，含答案](http://www.cnblogs.com/GT_Andy/archive/2009/12/25/1921911.html)
+ 2、[SQL Server面试题目精选，含答案](https://wenku.baidu.com/view/bd89bc2d915f804d2b16c154.html)