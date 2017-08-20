---   
layout: post    
title: Linux：shell编程的学习        
category: 技术    
tags: Linux     
keywords:      
description:     
---  

##  缘起
+ linux呢自己也算掌握一些知识，但一直吧没有太多的实践场景，shell呢，也差不多这种状态，以及呢还是看过鸟哥书中的shell部分，当时的笔记还是写在纸上的呢。

##  内容
###  chap1 Shell编程基础
+ 1.1 shell的功能与类型
	+ `echo $SHELL`和`grep $LOGNAME /etc/passwd`用于查看当前使用的shell。
	+ 用`sh`命令用于启动Bourne Shell，用`exit`退出。
	+ `ps -f`用于显示正在执行该脚本的Shell的名字。
+ 1.2 shell基本语法
	+ [ShellCode15.1](https://github.com/wolflion/GitHubCode/blob/master/ShellCode/SampleCode/chap15/15.1.sh)
	+ 注释、通配符【`?` `*` `[]` `{}` {}用得不太多】、重定向、管道`|`
		+ `{}`显示多种匹配结果。例`echo c{oon,op,ud}s`
		+ `2>`表示错误输出重定向；`&>`标准输出与错误输出重定向
		+ `|&`也可以与标准错误输出一起使用
	+ 前台与后台（`&`）运行
	+ 命令的执行顺序
	+ shell中3种引号
		+ 单引`''`：单引中所有的所有特殊字符都失去特殊意义。
		+ 双引`""`：在双引中，除了$,",`,\以外的所有字符都解释成字符本身。
		+ 反引：反引中的字符被解释成命令。     echo Today \' year is `date +%y`
	+ shell的3种运行方法
		+ `chmod 755 file ` 或 `chmod u+x file` 然后再`./file`
		+ `sh file` 或 `bash file`
		+ `source file` 或 `. file`

###  chap2 Shell变量及相关操作

###  chap3 条件测试

###  chap4 shell的控制结构
+ if
+ case
+ select
+ while
+ for
+ until
+ break和continue

###  chap5 函数

##  参考
+ 1、[《Linux Shell编程与编辑器使用详解》](https://book.douban.com/subject/24868431/) 
	+ 也就chap1、11-15是讲shell本身的，其它都是讲Linux环境配置以及命令的。	