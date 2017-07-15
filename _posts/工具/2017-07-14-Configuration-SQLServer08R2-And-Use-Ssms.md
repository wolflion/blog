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

###  内容
###  配置和使用SQLServer08R2
+ 1、2017-07-12 远程用smss.exe连SQLServer08R2，提示[Error26](http://www.jb51.net/article/35929.htm)，没有开启远程允许远程连接。
	+ 按提示的解决方案配置了，本机的smss可以访问，外面的还不行。因为这个环境部署在学校机房，初步定位是由于**学校机房的1433端口没开**，联系了一下学校机房，说是没开，让老师给他写邮件。*目前邮件已写，但还没答复呢。*
	+ 还可以再试试这个[参考](http://blog.csdn.net/tm308944952/article/details/24439889)
	+ [Foxtbable的帮助值得我们学习](http://www.foxtable.com/help/index.htm?page=2349.htm)
+ 2、[附加数据库失败，错误码5120](http://www.111cn.net/database/mssqlserver/69282.htm)

###  配置和使用Smss
+ 1、 2017-07-14 [用Smss写脚本时智能提示丢失了](http://www.cnblogs.com/dragonwlb/archive/2012/07/11/2586538.html)
	+ 参考链接解决了一下，*三台中有两台到第二步就可以了，唯独214上不行，我没敢安装08R2 SP1*，所以目前不能确认是08R2 SP1没安装导致214上不能用的。

###  基于以上的插件、小工具、常用功能