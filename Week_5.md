# 1. Algorithm

[Arithmetic Slices](<https://leetcode.com/problems/arithmetic-slices/>)

题目是要统计连续的等差数列的个数，且最小数量为3。

**我的解题思路：**

1. 从最低位开始，获取子字符串
2. 获取初始的差值
3. 若P+1中没有符合条件的数，则返回，否则当做连续数，做记录
4. 重复1-3，直到没有子字符串

```python
class Solution(object):
    def numberOfArithmeticSlices(self, A):
        """
        :type A: List[int]
        :rtype: int
        """
        sum_ = 0
        for begin in xrange(len(A)-1):
            slices = A[begin:]
            P = begin            
            
            count = 0
            differ = A[P+1] - A[P]
            count += 1
            while (P+1) < len(A):
                if A[P+1] - A[P] == differ:
                    count += 1
                    P += 1
                else:
                    break
                    
                if count >= 3:
                    sum_ += 1
        return sum_
```



**其他人的解题方法：Dynamic Programming**

假设有[1 3 5 7] 的数组，总共有3组符合的数列[1 3 5], [1 3 5 7], [3 5 7]。依次类推，当有[1 3 5 7 9]时也类似。此时多了3组：[5 7 9], [3 5 7 9], [1 3 5 7 9]。

那么加了9之后的这个数量是怎么算出来的呢？——注：加入后的9本身也符合条件。那么和[1 3 5 7]中的结果又有什么关系呢？[1 3 5 7], [3 5 7], [5 7]——即以7为结尾（上一组），且长度不小于2的都是符合条件的。也就是说，和上一组符合条件的子字符串的数量有关。——**数学归纳法的再一次演绎！！！**

```c++
class Solution(object):
    def numberOfArithmeticSlices(self, A):
        """
        :type A: List[int]
        :rtype: int
        """
        sum_ = 0
        dp = [0] * len(A)
        for begin in xrange(2,len(A)):
            if A[begin] - A[begin-1] == A[begin-1] - A[begin-2]:
                dp[begin] = 1 + dp[begin-1]
                sum_ += dp[begin]
        return sum_
```





# 2. Review

[The Best Questions to Ask at Your Performance Review](<https://medium.com/s/story/the-best-questions-to-ask-at-your-performance-review-5aba3fb86528>)

职场小白历险记：

很多企业可能会有专业性评估，那在此期间前以及期间能做哪些事情？

1. 明白企业的标准是什么
2. 这个是如何度量的
3. 我的优势和劣势，以及这个岗位的规划
4. 我要为企业创造更大价值——职业发展
5. 我能获得什么帮助，请求相关资源…
6. 薪水问题

# 3. Tips

遇事，保持冷静，仔细分析。——肾上腺素适用于体力事情，难以解决脑力方面的问题！

# 4. Share

[背包问题——贪婪算法](https://blog.csdn.net/VVBBBBB/article/details/89811644)

