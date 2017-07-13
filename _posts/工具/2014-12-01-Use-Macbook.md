---   
layout: post    
title: MacBook使用{未完}           
category: 工具      
tags: 工具     
keywords:      
description:     
---  

##  缘起
+ 2014-12-01入了个MacBook，由于平时还是使用Windows比较多，MacBook用得不算多，就记录一下操作方面的，这样查起来方便。

##  内容
###  Part1 系统使用
+ Mac中使用`Ternimal`想切换到root用户，[官网的答案](https://support.apple.com/zh-cn/HT204012)是这样的，还是用了`sudo passwd root`重设密码，当然还可以用`sudo -s`。
+ 安装app，就是把xxx.app拖进到`/Applications`，卸载就是在这个路径下删除掉。当然还可以用**清除软件CleanAPP**
+ **磁盘映像**文件类似于Windows下常用的iso文件，在OS里后缀名为dmg。几乎所有的安装程序都是以dmg方式发布的。
+ **状态保持**就是关机重启后重新打开程序并恢复到程序关闭前的状态。
+ **OS X的维护**，可以用`sudo periodic daily weekly monthly`命令。

###  Part2 快捷键
+ `ctrl+sapce`能呼出**Spotlight**
+ `F4`是**Launchpad**的快捷键。虽然看到的所有程序都像一个图标，但这不是Windows中的快捷方式，而是**封装好的Bundle**。
+ `command+space`切换输入法

###  Part3 Finder的使用
+ 选中文件后按**回车**是对*文件重命名*。
+ *文件打开*可以用**鼠标双击**和快捷键`Command+o`

###  Part4 用好工具
+ 日常工作
	+ 办公软件
		+ iWork
		+ OpenOffice
		+ Microsoft Office（收费）
	+ 邮件
		+ 重度Gmail可用 Sparrow和Unibox
		+ Foxmail情节的用 Foxmail for Mac
	+ IM
		+ 除了日常的，可以有整合工具Adium和Trillian
	+ 娱乐
		+ MPlayerX
		+ 射手影音（收费）
		+ VLC
	+ 下载 
		+ 命令行下用`wget`
		+ P2P软件可以用aMule
	+ 压缩
		+ iUnarchive
		+ The Unarchiver
		+ iPack（收费）
	+ 读书
		+ iBook
		+ EverNote
		+ Kindle for Mac
		+ ReadKit（收费）
		+ Pocket
	+ 虚拟机
		+ VirtualBox
		+ VMware Fusion（收费）
		+ Parallels Desktop（收费）
	+ 备份软件
		+ TimeMachine
+ 文本编辑器
	+ Vim
	+ Emacs
	+ TextMate
	+ Sublime Text
	+ Markdown
		+ Day One（收费）
		+ Byword（收费）
		+ Mou
	+ 文件比较
		+ FileMerge
		+ VisualDiffer（收费）
		+ `diff`和`vimdiff`命令
+ 资源管理器增强
	+ TotalFinder（收费）
	+ XtraFinder
	+ Breeze（收费）
	+ Window Tidy（收费）
+ 风扇控制
	+ smcFanControl

##  参考
+ 1、 [mac终端命令大全介绍](https://www.douban.com/note/75797151/)