---   
layout: post    
title: 写在重装win7系统后           
category: 工具      
tags: 工具     
keywords:      
description:     
---  

##  安装前
+ 备份数据

##  安装中
+ 直接在硬盘中安装的，无法格式化C盘。用PE进去格式化后，无法进入系统，只能用[老毛桃](http://www.laomaotao.org.cn/)做了一个U盘启动系统。
	+ *忘记了一个原理，就是从硬盘装到C盘的话，肯定是没办法格自己的啊。*
+ 安装好后用[驱动精灵](http://www.drivergenius.com/)安装了一下相应的驱动，以及激活了一下系统。
	+ 现在学会了**驱动的备份**，以及*整理的重用性*。
+ *手贱了一下*，拆了一下内存和硬盘区域，想着是不是再加个SSD盘的。然后[电脑打开屏幕不亮](https://zhidao.baidu.com/question/520328535.html)，只有硬盘灯亮和风扇响。
	+ *确认应该只有内存没插好，因为自己动了一下，换了一个口还是不行，折腾了两下，成功显示了。*

##  安装后的配置
+ 不想在自己的笔记本上安装sqlserver以及vs的开发工具，有情况还是远程比较好，基于这样的情况，稍微配置了一下。

###  绿色工具
+ everything
+ CCleaner
+ Sublime Text
+ Total Commander
+ beyondcompare

###  重要的工具
+ **github客户端**
	+ 之前用的是*Gtihub desktop*，主要觉得每次打开的时间太长，于是发现[TortoiseGit](https://tortoisegit.org/)支持github上取数据。*官网了下载，并下了个语言包，同时还要提前安装[git](https://git-scm.com/)。*
	+ 安装好后，发现右击时[没有tortoiseGit相应的选项](http://bbs.csdn.net/topics/320259352)。*开始以为是自己在setting里的配置问题，果然是重启治百病。*
        + 参考：[更新Svn客户端后，右键菜单中没有TortoiseSVN  ](http://qs52.blog.163.com/blog/static/210151592013111841954672)
    + 第一次还不太会用，网上找了个[方法](http://www.jb51.net/article/55440.htm),*这个虽然全吧，但没有说清楚*。又找了个相对说清楚的[方法](http://blog.csdn.net/yuanzichao/article/details/44922593)。
        + 用tortoiseGit自带的`PuTTYKey` 生成相应的key，拷贝到`github.com`的ssh Keys里去。
    + push了两次发现每次都要[输入用户名和密码](http://www.cnblogs.com/sapho/p/6140331.html)。
        + **修改了下本地的..gitconfig文件**里加了`[credential helper = store ]`
        + [网上的方案2](http://blog.csdn.net/kongjiea/article/details/40585869)