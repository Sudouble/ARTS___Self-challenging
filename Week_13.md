# 1. Algorithm

[12. Integer to Roman](https://leetcode.com/problems/integer-to-roman/)

数字转换为罗马数字——根据规则分别进行判断，可以很快得到一个可行解。具体的还待对代码近一步的优化。



**其他人的解决方案：**

1. 直接对特殊情况做处理——900、400、9、4等

# 2. Review

[Memory part 3: Virtual Memory](https://lwn.net/Articles/253361/)

虚拟内存相关内容，主要是讲了具体的实现方式。讲真，还真是不怎么看得明白为什么要什么设计。准备好好把计算机操作系统原理相关的知识补一补。——先把计算机算法课搞定之后！

虚拟地址的主要好处是可以保证进程之间的独立性，易于一个更高抽象层次的事务管理。相应也有一些trade off，因为内存地址是从直接访问变成了间接访问，而且随着进程运行时间的延长，会产生一些内存碎片（即内存中地址不连续的部分），这方面也是需要进行处理的。

![img](https://static.lwn.net/images/cpumemory/cpumemory.18.png)

且在内存也存在分配粒度的相关的事务需要进行处理，若分配太大，会造成内存的浪费，但是管理内存会更方便。分配粒度与空间寻址是一个相互作用的过程。

# 3. Tips

# 4. Share

[Windows DLL注入的方法介绍](https://blog.csdn.net/VVBBBBB/article/details/93773350)

