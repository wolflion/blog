---
layout: post  
title: lionel多线程笔记输出  
category: 技术  
tags: Linux      
keywords: linux     

description:    
---  

##  缘起
+ 主要是多线程自己一直不开窍，**了解基本用法吧**，但怎么使用又不太熟悉
+ 书的题目原型来自《C++并发编程实战》，并结合网上一些用例。

##  内容

###  0、基本概念

+ **互斥锁是用于同步线程对共享数据的访问的话，条件变量则是用于在线程之间同步共享数据的值**。
+ 如果一个函数能被多个线程同时调用且不发生竞态条件，则我们称它是**线程安全的（thread safe）**，或者说它是**可重入函数**。【**不可重入的原因，在于内部使用了静态变量**，可重入的版本后面会加个`_r`】

### 1、线程开始

#### 1.1、初步
```cpp
//https://github.com/xiaoweiChen/Cpp_Concurrency_In_Action/blob/master/content/chapter1/1.4-chinese.md
#include <iostream>
#include <thread>  //①
void hello()  //②
{
	std::cout << "Hello Concurrent World\n";
}
int main()
{
	std::thread t(hello);  //③
	t.join();  //④
}
```

#### 1.2、向线程函数传递参数
```cpp
void print(int n){
    cout<<n<<endl;
}

std::thread t2(print,10);
```

#### 1.3、转移线程所有权

#### 1.4、运行时决定线程数量
+ `std::hardware_concurrency()`

#### 1.5、其它
+ 类型`thread::id`
+ 不太懂的`detach()`啥作用？

### 2、共享数据保护（竞争条件）
#### 2.1、用mutex保护共享数据
+ *有竞争的时候，就得加锁*
+ 问题：
	+ mutex和lock_guard是啥关系？代码中`std::lock_guard<std::mutex>`这么用，有点类似于RAII机制
	+ **不需要自己再unlock()**
+ 其它方法
+ 问题2：
	+ lock_gurad()和unique_guard()的区别
		+ 参考：https://www.cnblogs.com/haippy/p/3346477.html 
		+ **都是模板类**
+ https://www.jianshu.com/p/8ff671d22aa8  c++11 多线程（2）mutex 总结
+ 深入理解mutex工作机制  https://www.jianshu.com/p/8d7d2d081adf
+ 互斥锁  https://baike.baidu.com/item/%E4%BA%92%E6%96%A5%E9%94%81/841823?fromtitle=mutex&fromid=6330198&fr=aladdin

#### 2.2、保护共享数据的其它方法

### 3、多线程异步
#### 3.1、同步方法-future，异步
+ `<future>` 头文件提供处理异步结果(在其他线程上执行额结果)的工具。
	+ `std::future`，`std::promise`，`std::packaged_task`，`std::async`
+ std::future 实例是MoveConstructible(移动构造)和MoveAssignable(移动赋值)，不过不能CopyConstructible(拷贝构造)和CopyAssignable(拷贝赋值)。
+ promise 对象可以保存某一类型 T 的值，该值可被 future 对象读取（可能在另外一个线程中），因此 promise 也提供了一种线程同步的手段。在 promise 对象构造时可以和一个共享状态（通常是std::future）相关联，并可以在相关联的共享状态(std::future)上保存一个类型为 T 的值。
https://blog.csdn.net/GreedySnaker/article/details/114289680 C++ 多线程异步(std::future )

https://cloud.tencent.com/developer/article/1584075  C++11异步编程(std::async, std::future, std::packaged_task, std::promise)

C++11并发与多线程笔记（9） async、future、packaged_task、promise  https://blog.csdn.net/Cxiao_mengxin/article/details/128989084

### 4、多线程同步
#### 4.1、条件变量

### 5、atomic

+ 以上是一些api使用，但如果**开发lock-free的算法和数据结构**, 就需要<atomic>头文件的内容
+ https://zhuanlan.zhihu.com/p/107092432  # C++11 - atomic类型和内存模型

### 6、内存模型
C++11 并发指南七(C++11 内存模型一：介绍) https://www.cnblogs.com/haippy/p/3412858.html

## 最后

### 参考

+ 1、[多线程系列](https://www.cnblogs.com/haippy/tag/multithreading/ ) *用的还是逐个讲解的方式，不利于把知识串起来怎么用，但掌握what应该是可以了*

### 履历

+ 2023-02-22整理一版

