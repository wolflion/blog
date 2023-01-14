---
layout: post  
title: lionel技术知识整理输出  
category: 学习    
tags: 编程语言        
keywords: CPP      

description:    
---  


##  缘起
+ NULL


##  内容

###  一、数据结构
+ 1、[绪论](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/01DataStruct/01%E7%BB%AA%E8%AE%BA.md)
+ 2、[线性表](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/01DataStruct/02%E7%BA%BF%E6%80%A7%E8%A1%A8.md)
  + 顺序表：**要先分配一段空间**，不管是用数组`int data[100]`，还是用`int *base=new int[100]`两种
  + 链表：
+ 3、[栈、递归、队列（受限的线性表）](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/01DataStruct/03%E6%A0%88%E3%80%81%E9%80%92%E5%BD%92%E3%80%81%E9%98%9F%E5%88%97.md)
+ 4、[串、稀疏矩阵、广义表](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/01DataStruct/04%E4%B8%B2%E3%80%81%E7%A8%80%E7%96%8F%E7%9F%A9%E9%98%B5%E3%80%81%E5%B9%BF%E4%B9%89%E8%A1%A8.md)
+ 5、[树与二叉树](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/01DataStruct/05%E6%A0%91%E4%B8%8E%E4%BA%8C%E5%8F%89%E6%A0%91.md)
  + 先序（**先根序**），其它2种定义类推
+ 6、[图](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/01DataStruct/06%E5%9B%BE.md)
  + 遍历：
    + 广度（**队列**辅助空间），
    + 深度（**栈**辅助空间），**后被访问的顶点，其邻接点先被访问**。
+ 7、[高级数据结构](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/01DataStruct/07%E9%AB%98%E7%BA%A7%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84.md)
  + B-树（B树）：
    + 二叉搜索树的树高会影响效率，**平衡二叉树搜索树**虽然减少了树高，但还是不行，于是有**多路平衡搜索树**【一个节点，不再限于只存一个关键字，而是**存多个关键字和多个子树**】
    + 一根m阶B-树满足以下特性：
      + 1）每个节点最多有m棵子树
      + 2）根节点至少有两根子树
      + 3）内部节点（除根和叶子之外的结点）至少有`m/2`(**取上界**）棵子树
      + 4）终端节点（叶子）在同一层上，并且不带信息（空指针），通常称为失败节点
      + 5）非终端节点的关键字个数比子数个数少1
  + B+树（不算传统的树了）
    + 一根m阶B+树满足以下特性：
      + 1）每个节点最多有m棵子树
      + 2）根节点至少有两根子树
      + 3）内部节点（除根和叶子之外的结点）至少有`m/2`(**取上界**）棵子树
      + 4）终端节点（叶子）在同一层上，并且不带信息（空指针），通常称为失败节点
      + 5）非终端节点的关键字个数**与子数个数相同**，*--lionel，这是差异点，6、7是新增-lionel*
      + 6）倒数第二层节点包含了全部的关键字，节点内部有序且节点间按升序顺序链接
      + 7）所有的非终端节点只作为索引部分，节点中仅含子树中的最大（或最小）关键字
  + 红黑树
    + 平衡二叉树（AVL树）**插入和删除**需要重新调整平衡，这里可能多达`O(logn)`次旋转，与之**左右子树高度差不超过1**，换成了，**左右子树高度差不超过2倍**，3次旋转后能达到平衡。
    + 红黑树（red-black tree）是满足以下性质的二叉搜索树：
      + 1）每个节点是红色或黑色的
      + 2）根节点是黑色的
      + 3）每个叶子结点是黑色的
      + 4）如果一个节点是红色的，则其孩子节点必为黑色
      + 5）从任一节点到其后代叶子的路径上，均包含相同数目的黑节点
+ 8、[排序](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/01DataStruct/08%E6%8E%92%E5%BA%8F.md)
+ 9、[查找](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/01DataStruct/09%E6%9F%A5%E6%89%BE.md)

### 二、操作系统

+ 1、[绪论](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/02OperationSystem/01%E7%BB%AA%E8%AE%BA.md)
+ 2、[操作系统运行环境](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/02OperationSystem/02%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F%E8%BF%90%E8%A1%8C%E7%8E%AF%E5%A2%83.md)
  + CPU相关知识，目态、管态
  + 中断、异常、系统调用
+ 3、进程管理
  + 3.1、进程与线程
  + 3.2、[进程同步与互斥](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/02OperationSystem/03%E8%BF%9B%E7%A8%8B%E7%AE%A1%E7%90%86-2%E5%90%8C%E6%AD%A5%E4%B8%8E%E4%BA%92%E6%96%A5.md)
    + 同步与互斥：
    + 临界区与临界区资源：
  + 3.3、[死锁](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/02OperationSystem/03%E8%BF%9B%E7%A8%8B%E7%AE%A1%E7%90%86-3%E6%AD%BB%E9%94%81.md)
    + 死锁的4个必要条件：互斥、不可剥夺、请求和保持、循环等待
    + 死锁预防：资源的静态分配（不可剥夺）、资源的有序分配（循环等待）
    + 死锁避免：**对资源申请进行动态检查**，银行家算法
    + 死锁检测：**存在“循环等等”条件**
    + 死锁解除：剥夺资源、撤销进程
    + 资源分配图
    + 哲学家就餐
+ 4、[存储管理](https://gitee.com/fewolflion/BookNote/blob/master/01lioneloutput/02OperationSystem/04%E5%AD%98%E5%82%A8%E7%AE%A1%E7%90%86.md)
  + 这里的存储更多是**内存**，因为多道程序设计（数据共享、进程通信），有了**分区**的想法，但如何引入**"虚存"**，又是如何实现的呢？
+ 5、文件管理
+ 6、I/O管理

### 三、算法

+ 1、绪论
+ 2、分治算法（divide-and-conquer）
  + 使用场景：二分、合并排序、快速排序、矩阵乘法、大整数乘法
  + 不适合分治算法的场景：
+ 3、贪心算法
+ 4、动态规划
+ 5、回溯算法
+ 6、分支界限算法

### C++面试题


##  履历
+ 2023-01月整理下 数据结构 相关知识