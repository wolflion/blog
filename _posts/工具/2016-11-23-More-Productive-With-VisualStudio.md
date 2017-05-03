---   
layout: post    
title: Microsoft Visual Studio的快捷使用方式{未完}           
category: 技术    
tags: 工具     
keywords:      
description:     
---  

##  缘起
+ 作为开发人员，日常工作中做得最多的就是两件事：**调试和编码**。

##  内容
###  chap1 现在开始
+ 1.3 导出环境设置
	+ 工具 | 导入和导出设置
+ 1.5 自动恢复
+ 1.9 更改Visual Studio的配色方案
+ 1.13 Visual Studio日志

###  chap5 查找
+ 5.1 重复查找
	+ 编辑 | 
	+ `F3`（下一个）；`Shift+F3`（上一个）
+ 5.2 使用快捷查找
+ 5.7 使用渐进式搜索
+ 5.15 查找符号结果的快捷键
	+ `F12`转到定义
	+ `Ctrl+F12`转到声明
	+ `Shift+F12`（`Ctrl+K,R`）查找所有引用
+ 5.16 在文件中替换：带标记的表达式

###  chap6 编码 
+ 6.1
+ 6.3 如何避免复制空行 
	+ 工具 | 选项 | 文本编辑器 | 所有语言 | 常规 | “没有选定内容时对空行应用剪切或复制命令”
+ 6.4 剪切或删除当前行 
	+ `Ctrl+L`（`Ctrl+X`）（`Shift+Del`） 剪切行
	+ `Ctrl+Shift+L` 删除行
+ 6.8 在网页中进行注释或取消注释
	+ `Ctrl+K,Ctrl+C` 注释
	+ `Ctrl+K，Ctrl+U` 取消注释
	+ 编辑 | 高级 | 
+ 6.9 在当前行前或行后插入空行
	+ `Ctrl+Enter` 行前
	+ `Ctrl+Shift+Enter` 行后
+ 6.35 使用大纲折叠到定义
	+ `Ctrl+M,Ctrl+O`
	+ 编辑 | 大纲显示 | 折叠到定义
+ 6.39 文档大纲：Web项目
	+ `Ctrl+Alt+T`
+ 6.45 使用代码段管理器
	+ `Ctrl+K,Ctrl+B`
	+ 工具 | 代码段管理器


###  chap7 调试
+ 7.1 通过代码设置断点
	+ C# `#if DEBUG System.Diagnostics.Debugger.Break(); #endif`
	+ C++ `#if _DEBUG _debugbreak; #endif`
+ 7.2 打开断点窗口
	+ 调试 | 窗口 | 断点
	+ 默认是 `Ctrl+Alt+B`
+ 7.4 禁用或启用所有断点
	+ 调试 | 
+ 7.5 在任务列表中使用TODO注释
+ 7.15 通过数据提示编辑值
+ 7.48 了解自动窗口

##  参考
+ 1、 [《快速编码》高效使用Microsoft VS](https://book.douban.com/subject/11529144/)