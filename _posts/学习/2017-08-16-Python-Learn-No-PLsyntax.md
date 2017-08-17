---   
layout: post    
title: Python学习之路(非语法本身)            
category: 学习            
tags: 总结        
keywords:      
description:     
---  

##  缘起
+ Python呢只是之前知道，并没有写过啥代码。2017年的8月初碰到个需要用Python写相关的*量化投资*实现，就自己开始看了看。

##  内容
###  环境准备
+ 安装[python](https://www.python.org/getit/)是msi文件，**选上pip和Add python.exe to Path**，不然后面要自己配置环境变量和pip命令不能用。
	+ `cmd`窗口下输入 `python -V`能显示出来版本号，就表示安装OK。
	+ 在不做修改的情况下`pip`命令只能在`C:\Python27\Scripts`下使用。
+ 安装pip
	+ [方法1](http://jingyan.baidu.com/article/b907e627a072a846e6891c5a.html)：下载[pip代码](https://pypi.python.org/pypi/pip#downloads)，解压以后，执行`python setup.py install`，再加入环境变量。
	+ [方法2](http://blog.csdn.net/qy20115549/article/details/52179800)：通过`Python27\Scripts`下的`easy_inatall pip`进行安装，同样需要加入环境变量。
	+ 参考
		+ [Python的包管理工具pip的安装与使用](http://blog.csdn.net/liuchunming033/article/details/39578019)
		+ [pip安装使用详解](http://www.ttlsa.com/python/how-to-install-and-use-pip-ttlsa/)
+ [安装.whl包](http://blog.csdn.net/u014365862/article/details/51817390)
	+ `pip install wheel`，然后再执行`pip install *.whl`即可。[whl文件下载](http://www.lfd.uci.edu/~gohlke/pythonlibs/)
+ 执行各种install过程中报的错，以及解决之道
	+ [“failed with error code 1” while installing scipy](https://stackoverflow.com/questions/30919393/failed-with-error-code-1-while-installing-scipy)下载了一个scipy的whl包到本地进行了安装。 	
+ 运行Python文件
	+ `cd`到源文件目录，`python *.py`
	+ 运行过程中遇到的缺少相应的库**[no module named numpy](https://stackoverflow.com/questions/7818811/import-error-no-module-named-numpy)**
		+ 在`C:\Python27\Scripts`下执行`pip install numpy`，安装成功后，在开发环境中输入`from numpy import *`，没有任何提示就表示安装成功。
		+ 还有[一种解决方案](http://www.360doc.com/content/13/0301/23/11621703_268763795.shtml)通过下载到本地进行安装，通过解压，然后执行`python setup.py install`进行安装。
+ 安装IDE
    + 网上的方案都是**[PyCharm](http://www.jb51.net/softs/541909.html)+vim插件**的方式，虽然我也比较喜欢用vim，但我是win环境，并且Pycharm安装好后，太耗内存了，实验室的电脑完全吃不消。
    + 也想过将**[Sublime Text3配置成IDE](http://python.jobbole.com/81312/)**，但是Mac系统的，太麻烦了。
    + 最后下载了个**[Spyder](https://bitbucket.org/spyder-ide/spyderlib/downloads/)**，但提示缺少PySide，于是用`pip install PySide`。

###  开发过程中的问题
+ 

##  参考
+ [安装Python](https://www.liaoxuefeng.com/wiki/001374738125095c955c1e6d8bb493182103fac9270762a000/001374738150500472fd5785c194ebea336061163a8a974000)
+ [Python的包管理工具pip的安装与使用](http://blog.csdn.net/liuchunming033/article/details/39578019)