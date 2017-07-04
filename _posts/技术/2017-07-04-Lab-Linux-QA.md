---
layout: post  
title: 实验室Linux环境中遇到的问题  
category: 技术  
tags: 总结     
keywords:      
description:     
---  

##  内容
+ 1、[Linux查看所有用户](http://www.cnblogs.com/lcword/p/5917426.html)
	+ 20170704 `cat /etc/passwd`
	+ [更全的](http://www.cnblogs.com/wangkangluo1/archive/2011/09/23/2185977.html) `cat /etc/passwd|grep -v nologin|grep -v halt|grep -v shutdown|awk -F":" '{ print $1"|"$3"|"$4 }'|more` *这个脚本我都不太懂*
+ samba服务是启动的，但`\\....\share`的方式访问不了，使用了xftp方式访问，用的是root登录的，但这个把所有路径都公开了，想[设置一个只能访问某个路径](http://blog.sina.com.cn/s/blog_4fd50c3901018a0l.html)。 
	+ *20170704还没试*
	+ [参考1](http://www.haiyun.me/archives/winscp-sftp-sudo-root.html); [参考2](http://blog.csdn.net/miltonzhong/article/details/43084191)