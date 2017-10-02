---
layout: post  
title: C语言：知识点整理 （未完）  
category: 学习    
tags: 编程语言        
keywords: C语言      
description:    
---  


##  缘起
+ **我目前思考的一点是：**自己弄清楚了这些细节之坑后，其实可能会忘记怎么去实现一个功能。【其实的学习步骤觉得更应该是先学正确的，然后去实现功能，最后再去把实现过程中遇到的坑再整理一下，*感觉我在学习的过程中有点本末倒置了*】
+ **自己整理的思想相当于以下逻辑**
    + 先把书读厚，把各个知识点，不仅仅是记住一个点，更要是从根上去理解它为什么这样。
    + 再把书读薄，根据读厚的点，整理成一个checklist，这样在编程实践中形成一个自己的规范。


##  内容
###  chap1 概述
+ 参考
    + 《C语言进阶》[chap01]

###  chap2 数据类型及其运算
+ 参考
    + 《125个建议》[chap01]
    + 《125个建议》[chap02]

###  chap3 选择语句和循环语句
+ 选择语句
    + if语句  
        + `==`和`=`；`else`配对；`;`不要乱用；少嵌套if；
    + switch语句
        + 不要忘记`break`和`default`；常用的`case`放前面；
    + `?:`避免嵌套
+ 循环语句
    + 少用`while`和`do-while`循环；多用`for`循环
        + `for`的细节和优化
    + `break`,`continue`，`goto`，`return`，`exit`的区别。
+ **谨慎与0值比较
    + 浮点、布尔、指针、整型它们所指的0都不一定是整型0。
+ 参考
    + 《125个建议》[chap3程序控制语句应该保持简洁高效](https://github.com/wolflion/GitHubCode/blob/master/C%26CPP/C/%E6%94%B9%E5%96%84C%E7%A8%8B%E5%BA%8F%E4%BB%A3%E7%A0%81%E7%9A%84125%E4%B8%AA%E5%BB%BA%E8%AE%AE/chap03%E7%A8%8B%E5%BA%8F%E6%8E%A7%E5%88%B6%E8%AF%AD%E5%8F%A5/chap03%E7%A8%8B%E5%BA%8F%E6%8E%A7%E5%88%B6%E8%AF%AD%E5%8F%A5.md)
    + 《C语言进阶》[chap03选择和循环结构的程序设计](https://github.com/wolflion/GitHubCode/blob/master/C%26CPP/C/C%E8%AF%AD%E8%A8%80%E8%BF%9B%E9%98%B6/chap03%E9%80%89%E6%8B%A9%E5%92%8C%E5%BE%AA%E7%8E%AF%E7%BB%93%E6%9E%84%E7%9A%84%E7%A8%8B%E5%BA%8F%E8%AE%BE%E8%AE%A1/chap03%E9%80%89%E6%8B%A9%E5%92%8C%E5%BE%AA%E7%8E%AF%E7%BB%93%E6%9E%84%E7%9A%84%E7%A8%8B%E5%BA%8F%E8%AE%BE%E8%AE%A1.md)
 
###  chap4 数组	
+ 参考
    + 《125个建议》[chap06]
    + 《C语言进阶》[chap04]

###  chap5 指针 
+ 参考
    + 《125个建议》[chap05]
    + 《C语言进阶》[chap05]

###  chap6 函数 
+ 参考
    + 《125个建议》[chap04]
    + 《C语言进阶》[chap07]

###  chap7 结构体与共用体
+ 参考
    + 《125个建议》[chap07]
    + 《C语言进阶》[chap06]

###  chap8 预编译处理和位段
+ 宏
	+ **带参宏与函数的区别**
+ 条件编译
+ 文件包含
+ 参考
    + 《125个建议》[chap10]
    + 《C语言进阶》[chap06]

###  chap9 文件   
+ 参考
    + 《125个建议》[chap09]
    + 《C语言进阶》[chap08]

###  chap10 断言与异常处理
+ 参考
    + 《125个建议》[chap11]
    + 《C语言进阶》[chap09]

###  chap11 其它
+ 《125个建议》
    + [chap08]
    + [chap12]
    + [chap13]
    + [chap14]
    + [chap15]
+ 《C语言进阶》
    + [chap10]
    + [chap11]  

##  履历
+ 目前参考的3本书
    + 李春葆主编[《新编C语言习题与解析》](https://book.douban.com/subject/24371347/)
    + 马伟著[《编写高质量代码》](https://book.douban.com/subject/26804602/)改善C程序代码的125个建议
    + 牟海军著[《C语言进阶》](https://book.douban.com/subject/11232781/)重点、难点与疑点解析
+ 更新时间
    + 2015-10-14左右完成整个框架。
    + 2017-10-02完成 *chap3程序控制语句*，并重新整理了一下框架。