---   
layout: post    
title: 配置SQLServer08R2和使用Ssms工具           
category: 工具      
tags: 工具     
keywords:      
description:     
---  

##  缘起
+ 2017-07-12 碰到了Ssms无法使用智能提示，虽然有好久没解决了，但想着解决一下吧，解决好后，就想着把这配置和使用方面的列个**工具**主题中，SQLScript就写到**技术**或**学习**里了。

##  内容
###  配置和使用SQLServer08R2

+ 1、2017-07-12 远程用smss.exe连SQLServer08R2，提示[Error26](http://www.jb51.net/article/35929.htm)，没有开启远程允许远程连接。
	+ 按提示的解决方案配置了，本机的smss可以访问，外面的还不行。因为这个环境部署在学校机房，初步定位是由于**学校机房的1433端口没开**，联系了一下学校机房，说是没开，让老师给他写邮件。开通1433后，*只有连`10.0.0.1`IP这种形式的才可以，而`10.0.01\Instance`这样的就不行*
	+ 还可以再试试这个[参考](http://blog.csdn.net/tm308944952/article/details/24439889)
	+ [Foxtbable的帮助](http://www.foxtable.com/help/index.htm?page=2349.htm)值得我们学习
	+ 用**netstat**查看1433端口的[占用情况](http://blog.csdn.net/dhmpgt/article/details/17523903)，这在定位问题过程中挺有用的呢。
		+ `netstat -ano`或`netstat -ano|findstr 1433`
		+ windows环境下 杀死进程号用`taskkill /pid 1433`，显示所有`tasklist /fi "pid eq 1433"`。
+ 2、[附加数据库失败，错误码5120](http://www.111cn.net/database/mssqlserver/69282.htm)
+ 3、在问题1的基础上，有调用我们视图的用户已经连上后反馈说`select * from ViewTable`取不到数据，我试了一下还真是，而`seletct * from [DBName].[dbo].ViewTbale`这样是可以取到的。*目前还没有解决。*
	+ [IIS上部署web 连接不上远程数据库问题](http://bbs.csdn.net/topics/390561166) *里面有提到用`ip\name,1433`的方式访问，但我还没试。*
	+ [iis部署后发生数据库连接超时错误](http://blog.csdn.net/strife/article/details/9130963) *我没让甲方试了在connection里加上`Pooling=true;Max Pool Size = 5120;Min Pool Size=0;`这段试试*。

###  配置和使用Smss
+ 1、 2017-07-14 [用Smss写脚本时智能提示丢失了](http://www.cnblogs.com/dragonwlb/archive/2012/07/11/2586538.html)
	+ 参考链接解决了一下，*三台中有两台到第二步就可以了，唯独214上不行，我没敢安装08R2 SP1*，所以目前不能确认是08R2 SP1没安装导致214上不能用的。

###  基于以上的插件、小工具、常用功能
+ 可以在Ssms上安装**SQL Prompt**用于智能提示。*SQL Assistant这个我没用过*

###  自己在项目中遇到的问题

###  要预研的问题
+ 1、[通过SQL Server 2008数据库复制实现数据库同步备份](http://www.cnblogs.com/dudu/archive/2010/08/26/1808540.html) *有两种方式*
	+ （1）借助于SQLServer2008R2本身的特性  [参考1](http://www.voidcn.com/blog/wangqi791975/article/p-4911812.html)，[参考2](http://jingyan.baidu.com/article/9f7e7ec0bc3bb76f2915544c.html)
	+ （2）一些公司的产品，比如“Oracle公司的GoldenGate”和“mirror镜像软件”


##  参考 