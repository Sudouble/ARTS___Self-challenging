# 1. Algorithm

[978. Longest Turbulent Subarray](https://leetcode.com/problems/longest-turbulent-subarray/)

较为brute force的解法，解答的思路是：看重本次搜索结果，只要不符合，就重新开始计算——和KMP算法有一定的相似性，但本题的情况完全不需要回溯。

**其他人的思路：**DP——利用缓存值，依次往上叠加

# 2. Review

[Memory part 2: CPU caches](<https://lwn.net/Articles/252125/>)

看完后，对CPU的缓存机制有了个一定的了解，以下为我看了之后的几个收获。

CPU为什么要有缓存，这和内存的速度有关，因为SRAM造价高昂，一般内存多为DRAM。而为了提升效率，又不得不使用SRAM，因此在多在CPU和内存之间级联多个SRAM缓存，主要架构如下图所示：

![](./imgs/cpumemory.2.png)

多为3级缓存，其中一级缓存最快，各级缓存主要分别用于数据和指令集。

而多级缓存的性能，不仅取决于空间，也受限于其他因素，以下为主要几个：

1. **多核处理器之间**：依靠几个简单的策略，就可以处理复杂的情况。

   ​	主要有以下几个：修改集（唯一有效集合）、专用集（单独使用）、共享集（共同访问）、未使用集。

   ​	只需要增加独立的几个引脚就可以检测到不同处理核心的缓存状态，非常方便——有限状态机内的状态转移关系。

   ![img](https://static.lwn.net/images/cpumemory/cpumemory.13.png)

2. **超线程的**

3. **数据预读**:  Prefetch

4. 总线速率：FSB——CPU至北桥

5. **内存速率**：内存和北桥之间

# 3. Tips

暂无

# 4. Share

暂无——预留：DLL注入相关