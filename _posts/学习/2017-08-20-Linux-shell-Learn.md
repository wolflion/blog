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
+ 2.1 Shell变量类型
    + 环境变量
        + HOME、PATH、TERM、PWD、PS1、PS2、SHELL、MAIL、LOGNAME、UID
        + `env`用于显示当前环境变量的值；用`set`可以设置相应环境变量的值。
    + 位置变量
        + `$0` ：对应当前执行的命令名（或Shell程序的文件名）。
        + `$1` ：对应第1个位置参数。
    + 预定义的特殊变量
        + `$#`：实际位置参数个数（不包括Shell脚本名）
        + `$*`：命令行中的所有位置参数组成的字符串
        + `$!`：上一个后台命令对应的进程号
        + `$?`：表示最近一条命令执行后的退出状态（返回值），为十进制数。
        + `$$`：当前进程号PID
    + 自定义变量
        + 字母或下划线开头，区别大小写
+ 2.2 变量操作
    + 创建和设置变量：`declare`和`typeset`用于创建变量。  
    + 删除变量：`unset`
+ 2.3 变量的赋值
+ 2.4 变量的输出
    + `echo`
    + `printf`：格式化输出变量
+ 2.5 数组变量
+ 2.6 算术运算（bsh没有内置的算术运算）
    + `expr`：变量前需要`$`符号
    + `let` ：变量前不需要`$`符号，但必须将单个的或者带有空格的表达式用双引号引起来。
    + `bc`或`awk`：进行更复杂的运算

###  chap3 条件测试
+ 3.1 测试命令
    + `test exp` 或者 ` [] `  **[]前后都要有空格**
+ 3.2 测试文件属性
+ 3.3 测试数组

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