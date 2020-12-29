---
layout: post  
title: 《Linux/Unix系统编程手册》  
category: 技术  
tags: Linux      
keywords: linux     

description:    
---  

##  缘起
+ 还是要花时间好好把这本书啃掉，之前人家说这是手册翻翻的，但我越来越觉得，通过这本书可以建立知识框架。

##  内容

### chap30、[线程：线程同步](https://www.cnblogs.com/fewolflion/p/14209297.html)

+ 1、互斥量和条件变量`pthread_cond_t`

### chap31、[线程：线程安全和每线程存储](https://www.cnblogs.com/fewolflion/p/14204253.html)

+ 1、什么是**线程安全**【多个线程同时调用】，什么是**可重入函数**【无需使用互斥量即可实现线程安全】。
+ 2、导致函数非线程安全的原因：**使用全局或静态变量**。
+ 3、保障非线程安全函数的方式：（1）用互斥锁对函数的调用；（2）仅在函数中操作共享变量的代码前后加入互斥锁。
+ 4、**线程特有数据**：使用相关API
  + `int pthread_key_create(pthread_key_t *key, void(*destructor)(void*))`
  + `int pthread_setspecific(pthread_key_t key, const void* value)`
  + `int *pthread_getspecific(pthread_key_t key)`
+ 5、**线程局部存储**：在全局变量声明时加入`__thread`关键字。

### chap32、[线程：线程取消](https://www.cnblogs.com/fewolflion/p/14209205.html)

## 履历
+ 20201228-chap31第一遍阅读和整理。

## 参考

+ 