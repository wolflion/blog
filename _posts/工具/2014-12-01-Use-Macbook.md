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
+ 利用好**触发角**，打开“系统偏好设置”->“Mission Control”->“触发角”，就可以对屏幕四个角进行设置了。
+ “Mission Control”设置中把“使窗口按应用程序成组”关掉，这样*不会把同一个程序的多个窗口叠在一起。*
+ 在触控板上，**双揸开合**即可显示你打开的标签页。
+ `top`显示目前系统的进程情况。但我本机安装不了**htop**，可以用`sudo port install htop`。按`q`退出。
+ 批量复制文件的时候，学会利用命令`cp *.png *.jpeg *.gif /destpath`
+ 程序切换`command+tab`或`command+shift+tab`。同组程序的切换`command+``
+ 远程复制 `scp`例`scp ./testfile.txt username@10.10.10.22:/tmp`
+ OS X中的ftp
	+ `ftp anonymous@ftp.mozilla.org`或者`sftp user@10.10.10.11`
	+ 第三方工具**FileZilla**
	+ 原生FTP工具，从Finder菜单栏进入“前往”->“连接服务器...”
+ 熟悉一下原生文档的**文档的版本控制**。
+ **快速发送带附件的邮件**，在文件上右击要发送的文件->“共享”->“电子邮件”即可。
+ **快速创建便签**，我们只需要选中文字，然后`shift+command+y`即可。
+ 打开多个窗口的情况下**保持原来的窗口永远在最上面**，只需要在拖其它窗口的时候按住command键就行。
+ **语音识别**，“系统偏好设置”->“键盘”->"听写"，*下次找不到某功能时，记得用搜索功能。*
+ **特殊字符输入**，记得用`option`+数字键那一排的。
+ **三指轻拍查找**，在单词上三指轻拍，就能出现单词解释。*还是英英的哦*，“系统偏好设置”->“触控板”。

###  Part2 快捷键
+ `ctrl+sapce`能呼出**Spotlight**
+ `F4`是**Launchpad**的快捷键。虽然看到的所有程序都像一个图标，但这不是Windows中的快捷方式，而是**封装好的Bundle**。
+ `command+space`切换输入法
+ `command+i`在文件或文件夹上输入这个命令时，可以在Spotlight注释功能中加入自己特定的关键词。
+ `sips -h`批量处理图片
+ `command+delete`删除Finder中选中文件，`shift+command+delete`会自动清空废纸篓。
+ `du -sh *`查看某个目录下各个文件和子目录各占多少空间。
+ `shift+command+3`全屏幕截图；`shift+command+4`通过鼠标截图；`defaults wirte com.apple.screencapture type -string JPEG`修改截图文件类型为jpeg，默认的是png。
+ 输入法的过程中`shift+6`可以输入表情符号，我装的五笔也可以用。
+ Safari中想在新的标签页打开网页时，只需要按住`command`键,单击链接即可。通过`shift+command`+左右方向键，可以快速在Safari中打开的标签中进行切换。
	+ **Safari的阅读器**，可以通过`shift+command+r`进入。当然还可以用Safari的插件**CustomReader**。
+ `history | grep apache`找到编号，但再执行一次的时候，只要输入!编号即可，如`!1001`。
+ 在当前应用程序时，可以用`command+n`再建一个。
+ 彻底退出当前应用程序，`command+q`
+ `shift+option+command+delete`直接清倒废纸篓。
+ 在终端中，想打开某个文件目录的Finder，可以使用`open`+路径
+ `pmset noidle`让电脑不进入休眠状态，关掉终端或`ctrl+C`可取消该命令。

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
+ 作者推荐的其它工具
	+ Go2Shell 
	+ CatchMouse
	+ F.lux调节屏幕色温

##  参考
+ 1、 [mac终端命令大全介绍](https://www.douban.com/note/75797151/)
+ 《MacTalk人生元编程》中的Mac Tips