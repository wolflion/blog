---
layout: post  
title: 网络编程之路  
category: 学习    
tags: 网络        
keywords: 网络编程      

description:    
---  

##  缘起

+ 想整理一下网络编程知识
+ 这《TCP/IP网络编程》的读书摘要（笔记），至少前2部分内容是，**只基于Linux啊，win下的不管**。
+ 我在读这本书之前呢，学过《unix/linux系统编程手册》，**简称TLPI**，所以里面有提到的内容，我没有忘记的，就一笔记带过

##  内容

### Part1、[开始网络编程](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/22NetworkProgamming/11TCPIP%E7%BD%91%E7%BB%9C%E7%BC%96%E7%A8%8B/Part01%E5%BC%80%E5%A7%8B%E7%BD%91%E7%BB%9C%E7%BC%96%E7%A8%8B.md)

+ chap1、理解网络编程和套接字
+ chap2、套接字类型与协议设置
+ chap3、地址族与数据序列
+ chap4-5、基于TCP的服务端/客户端
+ chap6、基于UDP的服务端/客户端
+ chap7、优雅的断开套接字连接
+ chap8、域名及网络地址
+ chap9、套接字的多种可选项
+ chap10、多进程服务器端
+ chap11、进程间通信
+ chap12、I/O复用
+ chap13、多种I/O函数
+ chap14、多播与广播

### Part2、[基于Linux的编程](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/22NetworkProgamming/11TCPIP%E7%BD%91%E7%BB%9C%E7%BC%96%E7%A8%8B/Part02%E5%9F%BA%E4%BA%8ELinux%E7%9A%84%E7%BC%96%E7%A8%8B.md)

+ chap15、套接字和标准I/O
+ chap16、关于I/O流分离的其他内容
+ chap17、优于select的epoll
+ chap18、多线程服务器端的实现

### Part3、《Linux高性能服务器编程》

+ chap08、[高性能服务器程序框架](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/22NetworkProgamming/12Linux%E9%AB%98%E6%80%A7%E8%83%BD%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%BC%96%E7%A8%8B/chap08%E9%AB%98%E6%80%A7%E8%83%BD%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%A8%8B%E5%BA%8F%E6%A1%86%E6%9E%B6.md)
  + 服务器解构为三个主要模块：**I/O处理单元、逻辑单元、存储单元**
  + 4种I/O模型：**阻塞I/O，非阻塞I/O要和（I/O复用、SIGIO信号）一起使用**
  + 两种高效的事件处理模式：**Reactor模式**（同步）和**Proactor模式**（异步）
  + 服务器模型：C/S和P2P
+ chap09、[复用I/O](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/22NetworkProgamming/12Linux%E9%AB%98%E6%80%A7%E8%83%BD%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%BC%96%E7%A8%8B/chap09%E5%A4%8D%E7%94%A8IO.md)
  + 3个函数：`select()、poll()、epoll()`
+ chap14、[多线程编程](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/22NetworkProgamming/12Linux%E9%AB%98%E6%80%A7%E8%83%BD%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%BC%96%E7%A8%8B/chap14%E5%A4%9A%E7%BA%BF%E7%A8%8B%E7%BC%96%E7%A8%8B.md)
  + POSIX的**信号量、互斥锁和条件变量**

### Part4、《UNP》卷1

+ chap25、[信号驱动式I/O](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/22NetworkProgamming/10Unix%E7%BD%91%E7%BB%9C%E7%BC%96%E7%A8%8B%EF%BC%88%E7%AC%AC2%E5%8D%B7%EF%BC%89/chap25%E4%BF%A1%E5%8F%B7%E9%A9%B1%E5%8A%A8%E5%BC%8FIO.md)
  + 这个倒没啥，就是个`SIGIO`信号
+ chap30、[客户服务器程序设计范式](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/22NetworkProgamming/10Unix%E7%BD%91%E7%BB%9C%E7%BC%96%E7%A8%8B%EF%BC%88%E7%AC%AC2%E5%8D%B7%EF%BC%89/chap30%E5%AE%A2%E6%88%B7%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%A8%8B%E5%BA%8F%E8%AE%BE%E8%AE%A1%E8%8C%83%E5%BC%8F.md)
  + *这个是重点*，lionel

### Part100、《Unix/Linux系统编程手册》[Part07（55-61章）](https://gitee.com/fewolflion/BookNote/tree/master/01lioneloutput/21UnixPrograming/07Part7Socket)

+ chap55、介绍
+ chap56、unix domain
+ chap57、tcp/ip网络基础
+ chap58、internet domain
+ chap59、服务器设计
+ chap60、高级主题

### 习题

+ 《TCP/IP网络编程》[习题](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/22NetworkProgamming/11TCPIP%E7%BD%91%E7%BB%9C%E7%BC%96%E7%A8%8B/%E8%AF%BE%E5%90%8E%E4%B9%A0%E9%A2%98.md)

##  最后

### 备注

+ 