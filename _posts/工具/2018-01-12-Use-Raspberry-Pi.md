---
layout: post    
title: 树莓派玩起来    
category: 工具    
tags: 技术          
keywords:      
description:     
---  

##  缘起
+ Raspberry Pi这个草呢大概是在2016年左右长起来的，2017年比较强烈想拔草，终于在2018-01-12收到了。
+ 当时还搜到**李凡希**译过这本书（毕竟之前见过，他可能不认识我），更觉得要入一个呢。

##  内容
###  前期运行起来
+ 装外壳（找店家要视频确认一下即可）
+ 具体我做了以下几步：参考的是[树莓派入门之装系统](http://blog.csdn.net/u011388550/article/details/49981703)
    + 格式化SD卡工具（可选）
    + Win32 DiskImager（必须） *将镜像写入sd卡*
    + 下载文件（必须） *desktop是完全版，lite应该是没有桌面的* 【我第一次用的是lite版】
    + ssh工具  
        + 我买的3b没有开启22端口，会提示`Could not connect to '192.168.1.108' (port 22): Connection failed.`。
        + 解决方案是**进入根目录，新建`ssh`的空文件就OK了**
###  连接系统
+ ssh连上后，用默认的账号`pi`和密码`raspberry`登录即可。
+ 开启root权限
    + 用vi编辑`/etc/ssh/sshd_config`文件，找到`PermitRootLogin`，之前这行是用`#`注释的，去掉注释，改为`PermitRootLogin yes`，重启一下sshd服务。
    + 执行`sudo passwd root`，输入密码，这样就可以用root登录了。
    + 写一个`hello.cpp`，用`g++`编译一下，没问题。
+ 配置wifi

###  tips
+ `sudo iwlist scan`用来扫描wifi

##  一些成体系的资料
###  链接
+ [树莓派实验室](http://shumeipai.nxez.com/)
###  书
+ 《爱上Raspberry Pi》 *电子版*【看完再评】
+ 《树莓派开发实战2nd》 *图书馆*【看完再评】
