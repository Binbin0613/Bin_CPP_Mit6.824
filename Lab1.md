### 6.824分布式系统C++实现—————Lab1:MapReduce

#### 1、预备知识
1、需要阅读的论文：[rfeet.qrk (mit.edu)](http://nil.csail.mit.edu/6.824/2020/papers/mapreduce.pdf)

2、需要git的仓库：git clone git://g.csail.mit.edu/6.824-golabs-2020 6.824

- LAB官方基于go实现，但代码一些注释的细节，整体框架以及测试情况需要了解，还是要download仔细阅读

3、环境配置

- 如果你用的go，直接按照[6.824 Lab 1: MapReduce (mit.edu)](http://nil.csail.mit.edu/6.824/2020/labs/lab-mr.html)的LAB1引导来做，如果和我一样C++选手，需要额外配置一下非STL的库（用于RPC），我个人没选择C库里 <rpc/rpc.h>下的RPC实现，感觉不是很方便。这里推荐下[github.com](https://github.com/button-chen/buttonrpc)的一个轻量级RPC库，需要安装zeromq和cppzmq的依赖，具体见[zeromq/cppzmq: Header-only C++ binding for libzmq (github.com)](https://github.com/zeromq/cppzmq)最底部的引导


#### 2、MapReduce基础框架

![image](https://user-images.githubusercontent.com/106053649/171107357-7042f8c9-a8cd-4643-a956-d71904add50f.png)

基本原理：
- MapReduce是一种编程模型，用于大规模数据集的并行运算。在分布式系统的背景下，首先需要明确各个执行Map任务和Reduce任务的计算机是不知道彼此的存在，他们只负责处理给予的任务并写入文件系统，也无法确保任务是否能顺利完成，故除了执行任务的worker以外，需要一个协调所有worker的master。
- master需要分配所有的任务，map阶段将需要处理的文件分配给执行map的worker，reduce阶段类似，在LAB1中是分配reduce任务编号。master还需实现状态的确认以及超时任务的重做（需要有定时任务处理），以确保任务阶段的变化以及失败任务的重新分发及处理。
- worker需要加载map及reduce函数，由于工作性质的不同，所以需要运行时动态加载，C/C++可以利用dlopen及dlsym来实现。具体的map及reduce工作，包括shuffle过程，建议看论文及视频，多思考思考。稍微提下一个容易想不明白的地方：执行recude的worker怎么知道他需要处理哪些文件呢？
  - LAB1的基本代码中有一个ihash函数，简而言之就是将map处理结果对recude总数取模，反映在lab1中可以体现为对所有words求和取模，后续拿到recude编号的worker读取对应尾缀的文件即可。
- 推荐一个介绍MapReduce基本原理的视频，[深入浅出讲解 MapReduce_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1Vb411m7go?spm_id_from=333.851.header_right.fav_list.click)可以在看完论文和6.824官方视频后加深理解。


#### 3、 RPC

#### 4、定时任务

#### 5、