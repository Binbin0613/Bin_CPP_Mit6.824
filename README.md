# Bin_CPP_Mit6.824
MIT6.824 distributed system C++Version

### 6.824分布式系统C++实现—————LAB1:MapReduce

原MIT6.824为go所写，个人技术栈主要为Java C++，秋招前再来一次，用C++实现各个Lab,参考：[tjumcw](https://github.com/tjumcw)

听说很锻炼能力，就尝试去做，但课程官网从有这门课开始就一直是基于go实现的LAB，想去找对应的测试脚本翻了翻网上没有一个C++版本。没办法，只能硬上，只能针对各种情况进行手动设计bug进行测试。而且C++实现起来相对较难，尤其在LAB2的Raft实现中麻烦了不少，实名羡慕goroutine，而且没有官方提供go实现的每个LAB最最基本的框架，完成LAB2后就准备记录一下自己的学习及code过程，希望能帮到大家，祝大家LAB顺利！


需要掌握的基本技能：
- Go语言基本语法：[1、go语言圣经](https://docs.hacknode.org/gopl-zh/index.html)，[2、go菜鸟教程](https://www.runoob.com/go/go-tutorial.html)，[3、go语言进阶](https://golang-minibear2333.github.io/books-share/)

- [ubuntu上配置相关环境](https://blog.csdn.net/guo_zhen_qian/article/details/134319002?fromshare=blogdetail&sharetype=blogdetail&sharerId=134319002&sharerefer=PC&sharesource=m0_46472374&sharefrom=from_link)

- [ubuntu教程](https://blog.csdn.net/weixin_45938441/article/details/124018485?fromshare=blogdetail&sharetype=blogdetail&sharerId=124018485&sharerefer=PC&sharesource=m0_46472374&sharefrom=from_link)

参考：
- 论文翻译： [MapReduce：Simplified Data Processing on Large Clusters（面向大型集群的简化数据处理）](https://www.cnblogs.com/fuzhe1989/p/3413457.html)

- 视频教程： [视频教程：MapReduce](https://www.bilibili.com/video/BV1Vb411m7go/?from=search&seid=8676892438131853528)