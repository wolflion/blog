---   
layout: post    
title: Linux{0}：系统架构与目录{未完}        
category: 技术    
tags: Linux     
keywords:      
description:     
---  

##  缘起
+ 2013-01-26就想读参考1了，直到2017-04-23偶然间在图书馆看到，借回来整理一下，同时也下到了电子版。
+ 虽然翻看的是图书馆借来的书，但页数标注的是电子版的，留着以下复习或更新用。
+ 作者用的是适用Kernel2.6以上版本，他自己用的系统是SuSE。
	+ 我目前远程到的环境是Debian，kernel是3.2。用`uname -a`查看。

##  内容
+ 目录 11/268  

###  chap0  
+ 启动流程
+ 关机流程

###  chap1 Linux目录和基本概念  32+0/268
+ [FHS定义的目录结构](www.pathname.com/fhs)
+ 根目录 `/`
	+ 根目录的建立（分成三步）
		+ Step0：之前的动作
		+ Step1：建立根目录所需的设备文件 提示符‘Creating root device.’
		+ Step2：先将该设备文件所指的位置（分割区）挂载到【/sysroot】目录下  提示符‘Mounting root filesystem.’
		+ Step3：切换目录到根目录下  提示符‘Switching to new root and running init.’
	+ 根目录的意义
		+ 笔者举的是“Fedora系统下如何进入SuSE”
	+ 根目录的目录清单
		+ `find / -maxdepth 2 -type d | wc -l` // 到3层会更多

###  chap2 不同启动模式的目录
+ 本地启动由GRUB应用程序支持；网络启动由PXE及TFTP应用程序所支持。
+ 2.1 本地启动`/boot`
	+ `ls -al /boot`显示所有文件
		+ 'config-*'
		+ 'grub'
		+ 'initrd*'
		+ 'System.map*'
		+ 'vmlinuz*'
		+ '*.zen*'：*是我的环境所没有的*。用于虚拟的操作系统启动
	+ 2.1.1 /boot/grub
		+ Stage1阶段
		+ Stage1.5阶段
		+ Stage2阶段
	+ 2.1.2 System.map文件
	+ 2.1.3 kernel及initrd
+ 2.2 远程启动`/tftpboot`

###  chap3 Kernel Sapce与User Space的桥梁--虚拟文件系统
+ Kernel Sapce与User Space的差别，**在于内存使用上安全机制的差异**。
	+ `head -100 /proc/iomem`
+ 3.1 设备文件目录 `/dev`
+ 3.2 程序信息与系统设置目录 `/proc`
+ 3.3 系统分类信息 `/sys` 

###  chap4 应用程序目录
+ 4.1 执行文件目录 `bin`和`sbin`
	+ **/bin 目录下所存放的是“所有用户”必要且可共同使用的执行文件**
	+ **/sbin 目录下的则是只有root管理员或一些服务程序等级才可以使用的系统执行文件。**
	+ **如果执行一些命令不行，先`echo $PATH`看看当前用户的默认路径是啥。**
+ 4.2 函数库目录 `lib`
	+ 不仅是个函数库目录，**更像是一个共享的软件仓库**，只要是供所有程序引用的文件，都可以归类到其中。
	+ 4.2.1 /lib/bdevid
+ 4.3 还原损坏文件目录 `/lost+found`
	+ `fsck` *我在debian系统重启时就提示我用这个命令*。
+ 4.4 额外安装软件目录 `/opt`
+ 4.5 用户共享目录 `/usr`
	+ 4.5.1 /usr/bin和/usr/sbin
	+ 4.5.2 /usr/etc
	+ 4.5.3 /usr/games
+ 4.6 临时目录 `/tmp`
	+ **与一般的目录差异在于其目录权限的配置，最后一位(用户组的执行配置)不是"x"，而是"t"。**

###  chap5 用户的主目录
+ **所有用户中，唯一主目录默认不放在/home下的是系统的管理员“root”。**
+ 5.1 `/home/name/`基本文件
	+ /home/name下的内容与`/etc/skel`下的内容完全一样
	+ `tail -3 /etc/passwd`可以看到用户指定的目录，同时可以修改一下
	+ 5.1.1 .bashrc及.bash_profile
	+ 5.1.2 .bash_history
		+ 主要记录用户曾经输入过的所有命令；但并不是实时的，而是在注销时，系统一次将所有该次登录的命令写入
	+ 5.1.3 .bash_logout
		+ 当用户注销的同时，系统会自动执行.bash_logout文件。
	+ 5.1.4 public_html
		+ 不是系统目录，*我的系统下就没有*，一般是自己的配置文件。
+ 5.2 `/home/name/`额外文件
	+ *作者提到的都是使用X_Window后，系统自动产生应有的目录和文件。*
	+ 5.2.1 X Window配置
	+ 5.2.2 X Window文件存放目录
		+ 系统默认的文件目录，有点类似于Windows系统下的。

###  chap6 系统配置目录
+ 6.1 `/etc`
+ 6.2 `/srv`
	+ 我自己电脑里这个目录下啥也没有，*笔者觉得应该是软件的预先规则。*

###  chap6 日志文件与媒体挂载目录 
+ 7.1 动态文件记录区 `/var`
+ 7.2 挂载用目录 `/meida`和 `/mnt`
	+ `/meida`主要服务于*移动存储设备*
	+ `/mnt`是早期使用的挂载目录，用于挂载*“文件系统”的目录*，比如ISO或NFS文件系统。
+ 7.3 自动挂载服务目录 `/misc`

##  收获
+ 2017-04-23花了2个多番茄钟的时间，通读了本书并整了下目录，觉得笔者把`/`所有内容列举了一下，自己看完了chap1和chap2后，全书则关注以下三个方面，以及自己grub时碰到的一个问题：
	+ （1）启动和关闭的流程
	+ （2）应用程序目录
	+ （3）系统配置目录 `/etc`
	+ 问题1：我们的debian系统在启动时，无法加载盘符，我只能等进入grub页面时，通过`E`进入编辑时，然后输入`Ctrl+X`再执行，我今天看了下，`/boot/grub/grub.conf`文件不存在啊。

##  参考
+ 1、[《Linux系统架构与目录解析》](https://book.douban.com/subject/3592797/) 
	+ 不太推荐没操作过Linux来看这本书，倒是推荐有操作经验的根据作者的思维建立自己的Linux主题方面的知识点。