### 6.824分布式系统C++实现—————Lab1:MapReduce

#### 1、预备知识
1、需要阅读的论文：[rfeet.qrk (mit.edu)](http://nil.csail.mit.edu/6.824/2020/papers/mapreduce.pdf)

2、需要git的仓库：git clone git://g.csail.mit.edu/6.824-golabs-2020 6.824

- LAB官方基于go实现，但代码一些注释的细节，整体框架以及测试情况需要了解，还是要download仔细阅读

3、环境配置

- 如果你用的go，直接按照[6.824 Lab 1: MapReduce (mit.edu)](http://nil.csail.mit.edu/6.824/2020/labs/lab-mr.html)的LAB1引导来做，如果和我一样C++选手，需要额外配置一下非STL的库（用于RPC），我个人没选择C库里 <rpc/rpc.h>下的RPC实现，感觉不是很方便。这里推荐下[github.com](https://github.com/button-chen/buttonrpc)的一个轻量级RPC库，需要安装zeromq和cppzmq的依赖，具体见[zeromq/cppzmq: Header-only C++ binding for libzmq (github.com)](https://github.com/zeromq/cppzmq)最底部的引导


#### 2、MapReduce基础框架

#### 3、 RPC

#### 4、定时任务

#### 5、