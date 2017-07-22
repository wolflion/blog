---
layout: post  
title: 从数据库开始重构老系统     
category: 技术    
tags: 项目      
keywords:        
description:       
---  

##  缘起
+ 其实重构这个项目，差不多自己在2017年初就开始写了，自己忽然意识到自己老解决问题只是进入舒适区，于是2017-07-21正好没有别的问题的打扰，开始好好重构一下代码。

##  内容
###  准备工作
+ 网了搜了一下*“如何从已有的DB生成Model代码”*，找了半天，其实并没有。找到了[Navicat Data Modeler](https://www.navicat.com.cn/products/navicat-data-modeler)，但它只能生成sql，无法配置相关EF里的关系那种。

###  Project模块
+ 最后还是用EF Code First[从旧数据库取出Project相关的内容](https://msdn.microsoft.com/en-us/library/jj200620(v=vs.113).aspx) ，正好这样的model，以及它的mapping属性都是一个参照，但可能我还不知道确切的意思是啥？
+ 20170721现状，项目相关的都可以做到增、删、改、查了，但不能导入老的数据，这个算v1.0版吧。


###  Fund模块




##  参考&收获 
###  文献
+ [Getting Started with Entity Framework 6 Code First using MVC 5](https://docs.microsoft.com/en-us/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/creating-an-entity-framework-data-model-for-an-asp-net-mvc-application)
+ [MVC-实体模型:EF CodeFirst 和  根据现有数据库生成Models ](http://blog.sina.com.cn/s/blog_6506a76001018mz7.html)