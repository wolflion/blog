---
layout: post  
title: 设计模式{0}：前置基础知识 （未完）  
category: 技术  
tags: 通用     
keywords: 设计模式   
description:    
---  

![UML](https://image.baidu.com/search/detail?ct=503316480&z=0&ipn=d&word=uml%E5%9B%BE%E7%89%87&step_word=&hs=2&pn=18&spn=0&di=81821994540&pi=0&rn=1&tn=baiduimagedetail&is=0%2C0&istype=2&ie=utf-8&oe=utf-8&in=&cl=2&lm=-1&st=-1&cs=733449665%2C1612643618&os=2869013448%2C4257137912&simid=2574923608%2C2307809362&adpicid=0&lpn=0&ln=1950&fr=&fmq=1492246245402_R&fm=detail&ic=0&s=undefined&se=&sme=&tab=0&width=&height=&face=undefined&ist=&jit=&cg=&bdtype=0&oriquery=&objurl=http%3A%2F%2Fimg.my.csdn.net%2Fuploads%2F201301%2F26%2F1359204528_4308.jpg&fromurl=ippr_z2C%24qAzdH3FAzdH3Fks52_z%26e3Bvf1g_z%26e3BgjpAzdH3Fziwg2ytg23tjalAzdH3Fw6ptvsjAzdH3F1jpwtsfAzdH3Fbcn9a8b&gsm=0&rpstart=0&rpnum=0)

##  缘起
+ 不知道是以前没用心学，还是书选得不对，还是方法不对，对于设计模式总是一知半解和一头雾水，16年上开了设计模式这门课，我虽然没选，但我还是去上了，虽然只是讲了23个模式中的部分，但我感觉设计模式算是入门了，所以想写个设计模式系统系列，算是自己的总结和笔记，也分享给大家。

##  内容
+ 前置基础知识，需要了解两方面的知识
	+ UML(Unified Modeling Language)
	+ OOD(Orient Object Design)

###  UML建模
+ UML类图中的基本元素符号
	+ 类
		+ 类名 *斜体是抽象类*
		+ 属性
		+ 方法
			+ `+`是public
			+ `-`是private
			+ `#`是protected
	+ 接口
		+ *斜体，并用`<<interface>>`修饰*
	+ 注释
+ [类与类之间的关系](http://blog.csdn.net/tianhai110/article/details/6339565)
	+ Generalization泛化关系（继承）
		+ 描绘子类与父类的关系 *实线空心三角*
	+ Realization实现关系
		+ 类实现接口 *虚线空心三角*
	+ Dependency依赖关系
		+ *虚线箭头*
	+ Association关联关系
		+ 单向关联：*实线箭头*
		+ 双向关联：*实线*
		+ 自关联：*实线箭头*
	+ Aggregation聚合关系
		+ has-a关系，*空心菱形，实线箭头*
	+ Composition组合关系
		+ contains-a关系，*实心菱形，实线箭头*

###  OOD
+ 2个基本原则
	+ Composite Reuse Principle 合成复用原则
	+ 针对接口编程，而不是针对实现编程
+ 5个设计原则
	+ Single Responsibility Principle 单一职责原则
	+ Open/Close Principle 开放/封闭原则
	+ Liskov Substitution Principle 里氏替换原则
	+ Interface Segregation Principle 接口分离原则
	+ Dependency Inversion Principle 依赖倒置原则

##  复盘&致谢
+ 我之前对知识的学习呢，一开始就先记这些词或原则，并没有先去实践，导致一些词有听过，但不明白真正是啥意思。*现在先是知道词后，先去实践和理解，然后再做笔记输出。*
+ 在胡乱的瞎学之后呢，还是需要回来再重头整理一遍，是对自己学习结束后一种总结，也是一种分享。
	+ 我最先开始读的是Gof的《设计模式》，又没有去理解好一些前置知识，导致学得吃力，效果还不好。
+ 现的情况，结合C#语言，用**代码和工具**，以及一些**应用场景**,去串联起这些知识。
+ 整理这些知识点的原型书型
	+ 于卫红[《Java设计模式》](http://product.dangdang.com/24043255.html) chap1-3