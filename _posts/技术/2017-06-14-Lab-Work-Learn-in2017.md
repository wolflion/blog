---
layout: post  
title: 2017年：实验室工作与学习  
category: 技术  
tags: 总结     
keywords:      
description:     
---  

##  工作

##  学习

###  基础知识

###  编程语言 

###  前端相关

###  工具类
+ MinGW、Cmder、g++
    + 错误1“ [cannot open output file a.exe](https://zhidao.baidu.com/question/536410790.html) ”
        + a.exe在窗口被打开，如果任务栏看不到，进程里kill掉。
    + 错误2“[undefined reference to `WinMain@16](http://blog.csdn.net/chuck_0430/article/details/8824762) ”
        + `int main()`时，main写成mian或者maian啥的了。  

##  同门汇报收获&触发的思考
###  2017-06-14上半年（*主要只记了一下我想关注的*）
+ 周行
	+ SSH框架介绍
		+ Struts.xml实现了对无效请求的过滤。
		+ Spring：融合了IoC和DT的功能。
		+ Hibernate：是jdbc的轻量封装，把对数据库的操作转换成对持久化对象的操作。*SessionFactory*
	+ 规则数据库
	+ 工具
		+ [PHPMyAdmin](https://www.phpmyadmin.net/)
			+ 是MySQL的管理工具，同样也有navicat工具。
			+ 虽然有轻量级的*Navicat for SQL Server*，但微软自带的SSMS功能更强。
		+ [Zabbix](http://www.zabbix.com/)：资源线上监控
	+ 他们目前的系统
		+ 4台机器，提供了主备份机制，如果宕机，会使用数据漂移的方式来迁徙数据。*但如果主备份OK的话，应该可以实时切换的啊？逻辑上是这样。*
		+ 他们的机房环境，是硬件上安装虚拟机，然后再进行软件的安装，这样移植和维护方便。
+ 闻金华
	+ 提到一个问题：Extjs2.0不能发送异步请求。*这个要看文档确认下。*
	+ 提到项目中，要替换成通用模板时，用的`Ctrl+H`的方式，其实就算写个工具也不会比`Ctrl+H`有更快的，看看有无更好的解决方案。
+ 窦方坤
	+ **一键发布**提到的是[web deploy3.6](https://www.iis.net/downloads/microsoft/web-deploy)是微软官方的，我也搜到了TTautoDeploy，在目前项目中应用一下。
		+ [VS 2015 Web Deploy 发布项目到远程IIS](http://jingyan.baidu.com/article/7908e85ca6db2daf491ad27e.html)
	+ 虽然不觉得TFS（TeamFoundationServer）多6，但自己也算git的重度用户，还是要再深入了解git与版本工具的区别，复试的时候防身用。
+ 李红岩
	+ 存在多次输入sql，输出excel文档的情况，在github上有了[sql2Excel](https://github.com/search?utf8=✓&q=sql2excel&type=)的例子，自己也想实践一下。
+ 郑新宇
	+ 告诉我们说**Admin lte**算是个模板工具。