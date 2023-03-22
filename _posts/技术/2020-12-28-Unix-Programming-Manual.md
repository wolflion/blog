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

# [Linux/Unix系统编程手册 第三章：系统编程概念](https://www.cnblogs.com/pluse/p/6296992.html)

https://man7.org/tlpi/code/online/book/lib/error_functions.h.html



https://cloud.tencent.com/developer/news/106022 抄一下目录

##  内容

+ [gcc入门](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/21UnixPrograming/0gcc%E5%85%A5%E9%97%A8.md)
+ 要问自己4个问题
  + more命令能做什么？**分析程序**
  + more命令是如何实现的？**学习系统调用**
  + 能不能自己编写一个more命令？**编程实现**
  + 代码还能不能再优化？

### 一、01Linux背景知识及概念

### 二、系统编程接口的基本特性（4-12）

#### [chap04、文件I/O：通用的I/O模型](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/21UnixPrograming/02Part2IO/chap04%E6%96%87%E4%BB%B6IO%E9%80%9A%E7%94%A8%E7%9A%84IO%E6%A8%A1%E5%9E%8B.md)

- open()拿到一个fd，然后read()、write()，用close()释放
- **对于已打开的每个文件，内核都维护有一个文件偏移量**，这决定了下一次读或写操作的起始位置。
- **在文件原结尾处之后的某一个位置写入数据将导致文件空洞**（*lionel，这个怎么实现？*）
- **未纳入标准I/O模型的所有设备和文件，ioctl()是个“百宝箱”**

#### [chap05、深入探究文件I/O](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/21UnixPrograming/02Part2IO/chap05%E6%B7%B1%E5%85%A5%E6%8E%A2%E7%A9%B6%E6%96%87%E4%BB%B6IO.md)

chap06、

chap07、

chap08、

chap09、

chap10、

chap11、

#### [chap12、系统和进程信息](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/21UnixPrograming/02Part2IO/chap12%E7%B3%BB%E7%BB%9F%E5%92%8C%E8%BF%9B%E7%A8%8B%E4%BF%A1%E6%81%AF.md)

+ /proc文件系统向应用程序暴露了一系列内核信息。`/proc/PID子目录`
+ `uname()`获取UNIX的实现信息以及应用程序所运行的机器类型

### 三、系统编程接口的高级特性（13-23）

#### chap13、文件IO缓冲

+ 在Linux环境下，`open()`所持有的**`O_DIRECT`** 标识允许特定应用跳过缓冲区高速缓存。

#### chap14、

+ 设备都由`/dev`下的文件表示
+ 特权级进程可使用`mount()`和`umount()`系统调用来挂载、卸载文件系统。可使用`statvfs()`来获取与已挂载文件系统有关的信息

#### chap15、

+ 程序可调用utime()、utimes()或类似编程接口，去更改文件的上次访问时间及上次修改时间
+ 每个文件都有一个与之相关的用户ID（属主）和组ID，以及一组权限位。
+ I节点标记控制着文件和目录的各种行为。

chap16、

chap17、

chap18、

chap19、

#### chap20、

+ 信号是发生某种事件的通知机制
+ 信号传递通常是异步行为
+ 发送信号：`kill()`
+ 接收信号：`pause()`

chap21、

chap22、

#### chap23、

+ 进程可以使用setitimer()或alarm()来设置定时器
+ Linux 2.6所实现的POSIX.1b扩展为高精度时钟和定时器定义了一套API
+ Linux特有的timerfd API提供了一组创建定时器的接口，与POSIX定时器API相类似，但允许从文件描述符中读取定时器通知

### 四、进程、程序及线程（24-33）

#### chap24、

+ 系统调用fork()通过复制一个与调用进程（父进程）几乎完全一致的拷贝来创建一个新进程（子进程）。
+ **系统调用vfork()应避免使用**，vfork产生的子进程将使用父进程的内存，直至其调用exec()或退出，于此同时，将会挂起（suspended）父进程。
+ 调用fork()之后，不应对父、子进程获得调度以使用CPU的先后顺序有所依赖。

#### chap25、

+ 进程的终止分为正常和异常两种，异常会导致core dump。
+ 正常的终止可以通过调用_exit()完成，更多的情况下，使用`_exit()`的上层函数`exit()`，两者都需要一个整型参数，**低8位定义了进程的终止状态**，状态0表示进程成功完成，非0则表示异常退出。
+ 不管进程正常终止与否，内核都会执行多个清楚步骤。**调用exit()正常终止一个进程，将会引发执行经由atexit()和on_exit()注册的退出处理程序（执行顺序与注册顺序相反），同时刷新stdio缓冲区**。

#### chap26、

+ 使用wait()和waitpid()（以及其他相关函数），父进程可以得到其终止或停止子进程的状态。
+ 如果子进程的父进程终止，那么子进程将变为**孤儿进程**，并为进程为1的init进程接管
+ 子进程终止后会变成僵尸进程，仅当其父进程调用wait()（或类似函数）获取子进程退出状态时，才能将其从系统中删除。
+ 捕获终止子进程的一般方法**是为SIGCHILD设置信号处理程序**。

#### chap27、

+ 进程可使用`execve()`以一新程序替换当前增长运行的程序，**允许为新程序指定参数列表（argv）和环境列表**。
+ 所有的exec()函数均可用于加载二进制的可执行文件或是执行解释器脚本。
+ 脚本的起始行（`以#!开头`）指定了解释器的路径名，供识别解释器之用。如果没有这一行，**只能通过execlp()或execvp()来执行脚本，并默认把shell作为脚本解释器**。

#### chap28、

+ 当打开进程记账功能时，内核会在系统中每一进程终止时将其账单记录写入一个文件。该记录包含进程使用资源的统计数据。
+ 如同fork()，clone()系统调用也会创建一个新进程，但其对父子间的共享属性有更为精准确的控制。该系统调用主要用于线程库的实现。
+ **尽管vfork()要快于fork()，但较之于子进程随后调用exec所耗费的时间，二者间的时间差异也就微不足道了**。

#### [chap29、线程：介绍](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/21UnixPrograming/04Part4ProcessThread/chap29%E7%BA%BF%E7%A8%8B-%E4%BB%8B%E7%BB%8D.md)

+ 在多线程程序中，多个线程并发执行同一程序。**所有线程共享相同的全局和堆变量**，但每个线程都配有用来存放局部变量的私有栈。同一进程中的线程还共享一干其他属性，**包括进程ID、打开的文件描述符、信号处置、当前工作目录以及资源限制**。
+ 线程与进程之间的关键区别在于：**线程比进程更易于共享信息**。
+ 可使用pthread_create()来创建线程。每个线程随后可调用`pthread_exit()`独立退出（**如有任一线程调用`exit()`，那么所有线程将立即终止**）。**除非将线程标记为分离状态`pthread_detached()`，其他线程要连接该线程，则必须使用`pthread_join()`，由其返回槽连接线程的退出状态**。

#### [chap30、线程：线程同步](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/21UnixPrograming/04Part4ProcessThread/chap30%E7%BA%BF%E7%A8%8B-%E7%BA%BF%E7%A8%8B%E5%90%8C%E6%AD%A5.md)

+ 多线程应用程序必须使用**互斥量和条件变量**等同步原语来协调对共享变量的访问。**互斥量提供了对共享变量的独占式访问**。**条件变量允许一个或多个线程等候通知：其它线程改变了共享变量的状态**。

#### [chap31、线程：线程安全与每线程存储](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/21UnixPrograming/04Part4ProcessThread/chap31%E7%BA%BF%E7%A8%8B-%E7%BA%BF%E7%A8%8B%E5%AE%89%E5%85%A8%E5%92%8C%E6%AF%8F%E7%BA%BF%E7%A8%8B%E5%AD%98%E5%82%A8.md)

+ 若一个函数可由多个线程同时安全调用调用，则称之为线程安全的函数。
+ **使用全局或静态变量**是导致函数非线程安全的通常原因。

#### [chap32、线程：线程取消](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/21UnixPrograming/04Part4ProcessThread/chap32%E7%BA%BF%E7%A8%8B-%E7%BA%BF%E7%A8%8B%E5%8F%96%E6%B6%88.md)

+ 函数pthread_cancel()允许某线程向另一个线程发送取消请求，要求目标线程终止。
+ 目标线程如何响应，取决于其取消性状态和类型。**如果禁用线程的取消性状态，那么请求会保持挂起（pening）状态，直至将线程的取消状态置为启用**。
+ 线程可以设置一个清理函数栈

#### [chap33、线程：更多细节](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/21UnixPrograming/04Part4ProcessThread/chap33%E7%BA%BF%E7%A8%8B-%E6%9B%B4%E5%A4%9A%E7%BB%86%E8%8A%82.md)

+ 不要将线程与信号混合使用，只要可能多线程应用程序的设计应该避免使用信号。

### 五、进程及程序的高级主题（34-42）

chap34、

chap35、

chap36、

chap37、

chap38、

chap39、

chap40、

chap41、

chap42、

### 六、进程间通信（43-55）

#### chap43、进程间通信简介

#### chap44、管道和FIFO

#### chap45、System V:IPC介绍

#### chap46、System V:消息队列

#### chap47、System V:信号量

#### chap48、System V:共享内存

#### chap49、内存映射

#### chap50、虚拟内存操作

#### chap51、POSIX:IPC介绍

#### chap52、POSIX:消息队列

#### chap53、POSIX:信号量

#### chap54、POSIX:共享内存

#### chap55、POSIX:文件加锁

### 七、套接字及网络编程（56-61）

#### chap56、[socket：介绍](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/21UnixPrograming/07Part7Socket/chap56SOCKET-%E4%BB%8B%E7%BB%8D.md)

+ 大多数应用程序使用流socket和数据报socket中的一种。
+ 一个典型的流socket服务器
+ 一个典型的数据报socket服务器

#### chap57、[socket：unix domain](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/21UnixPrograming/07Part7Socket/chap57SOCKET-UNIX%20DOMAIN.md)

+ UNIX domain socket是通过文件系统中的一个路径名来标识的。

#### chap58、[socket：TCP/IP网络基础](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/21UnixPrograming/07Part7Socket/chap58SOCKET-TCPIP%E7%BD%91%E7%BB%9C%E5%9F%BA%E7%A1%80.md)

#### chap59、[socket：Internet domain](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/21UnixPrograming/07Part7Socket/chap59SOCKET-Internet%20DOMAIN.md)

#### chap60、[socket：服务器设计](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/21UnixPrograming/07Part7Socket/chap60SOCKET-%E6%9C%8D%E5%8A%A1%E5%99%A8%E8%AE%BE%E8%AE%A1.md)

#### chap61、[socket：高级主题](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/21UnixPrograming/07Part7Socket/chap61SOCKET-%E9%AB%98%E7%BA%A7%E4%B8%BB%E9%A2%98.md)

### 八、高级I/O主题（62-64）

#### chap62、

#### chap63、其它备选的I/O模型

+ I/O多路复用（select()和poll()）、信号驱动I/O以及Linux专有的epoll API。所有这些机制都允许我们监视多个文件描述符，以查看哪个文件描述符上可执行I/O操作。**并不实际执行I/O操作**，一旦发现某个文件描述符处于就绪态，我们仍然采用传统的I/O系统调用来完成实际的I/O操作。
+ **如何在监视多个文件符的同时等待信号的发送？** 解决方案是**self-pipe的技巧**（即信号处理例程写一个字节数据到管道中，代表管道读端的文件描述符包含在被监视的文件描述符集合中。）

#### chap64、

## 履历
+ 20201228-chap31第一遍阅读和整理。

## 参考

+ ### chap30、[线程：线程同步](https://www.cnblogs.com/fewolflion/p/14209297.html)

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