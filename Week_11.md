# 1. Algorithm

[82. Remove Duplicates from Sorted List II](<https://leetcode.com/problems/remove-duplicates-from-sorted-list-ii/>)

题目总体耗时2小时，why？只是在脑子里演练了一遍就开始写了，其实这时候还没有做好具体的推演，写起来一片混乱。

什么是程序？——算法+数据结构

算法本身都没有搞清楚，怎么可能写得出能工作的程序呢？!



题目本身不是很复杂，要做得话有两个思路：

1. 链表直接求解
2. 还原成数组，再做分解。
   1. ——数据结构：(number, count)
   2. 算法：只记录是否与前一位数重合，若重合，则前一位数与当前位的计数加一



总结：**理清思路**，再下手，并且下手前要准备好**测试样例**，不求多，但尽量全面

# 2. Review

[What every programmer should know about memory, Part 1](<https://lwn.net/Articles/250967/>)

文章介绍关于计算机组成原理方面的知识。

这里主要讲了南北桥的作用，北桥主要用于高端设施：CPU、内存，南桥主要用于PCI-E、USB、SATA等数据的传输与通信。

CPU、内存相关，其中着重介绍了内存。以前只知道SRAM，DRAM的名称，现在是理解了，都是和数电、模电相关的知识。SRAM和TTL电路类似，但是造价成本高，于是常见于CPU缓存、高性能路由器中。而DRAM的造价成本低，但也有一定的约束，这个由硬件电路中的电容决定，需要一定的充放电时间。

以及后面也介绍了SDR、DDR、DDR2、DDR3等技术，确实是开阔了不少的视野。期待后面相关的几篇文章。

**组成一台计算机关键的制约因素还是在于成本！**

# 3. Tips



# 4. Share

Windows DLL注入的几种方式——跨进程（不同的进程地址空间）