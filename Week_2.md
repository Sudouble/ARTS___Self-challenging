# 1. Algorithm

​	[LeetCode: Container With Most Water](<https://leetcode.com/problems/container-with-most-water/>)

根据不同的输入，计算最大的需水量。这个题还是典型的两种解法，一种是brute force，另一种个人认为是属于贪心算法了。

- Brute Force——第一下就想到这个穷举方法
- 两端逼近法。我们的主要目标是找到最大的面积，于是可以分两步走，第一步找最大的宽度，第二步找最大的高度。最大宽度肯定就是从两边往两处找了，而且找的时候是将最短边的那出给替换掉。遍历一遍，就能找到最大面积了。


```c++
class Solution {
public:
    int maxArea(vector<int>& height) {
        int areaMax = 0;
        
        int start = 0;
        int end = height.size()-1;
        while (start < end){
            int distance = end - start;
            int high = min(height[start], height[end]);
            int area = distance*high;
            if (area > areaMax)
            {
                areaMax = area;
            }
            if (height[start] >= height[end]){
                end--;
            } else {
                start++;
            }
        }
        return areaMax;
    }
    
};
```



# 2. Review

[How to teach yourself programming in ten years](<https://arantius.com/misc/mirror/TeachYourselfProgramming.html>)

​	十年看上去很长，实际走下来，却可能很短。从我自己开始接触Coding到现在也已近7年了，虽然中间加入了很多其他的事情，但总体上是把基本的语法学到了，也用过了一部分。关于如何规划未来的这几年，最根本的还是需要先让自己静下心来，**别**天天这个那个的**学习焦虑症**，对未来的自己至少要有一个认识和了解。比如，你自己最怕接触到的事情是什么，先把这些怕，但很有用的东西克服了（比如基础知识），至少在后面会少很多磕磕绊绊。

​	作者在文中也提到了，要做好一件事，首先需要兴趣（未来自己的动力来源），其次再考虑其他的。学习一门基本语言固然重要，但学习语言不就是为了和人交流、进一步促进自己成长的吗？向优秀的人看齐，学习他们散发的优点。

- 找到兴趣爱好点
- 走出舒适区，并坚持实践：学好一件事情没有太多的捷径，对于结合实际的要的是挑战自己能力水平的上限，不断磨练、精进
- 打好基本功
- 与人交流
- 学习他们优秀的部分（如Coding风格等）

借用庄子的话来说，“吾生也有涯，而知也无涯，以有涯随无涯，殆矣。”

# 3. Tips

以前对多线程很迷，不知道要怎么操作，最近开始通读《Windows核心编程》，学习到了很多的新知识，在此做个小归纳。

Windows下的c++多线程编程，创建线程的几个主要函数

- _threadstartex(...)
- CreateThread(...)
- AfxBeginThread(...)

_threadstartex使用的是C/C++运行库，AfxBeginThread是MFC的运行库，CreateThread是windows提供的API函数。这里主要介绍前两个函数，MFC函数实际上是调用了__threadstartex来创建线程。

那么为什么要有_threadstartex函数呢？因为早在70年代C语言发明之初，没有多线程编程这一说，所以有很多库函数（如strstok等）都不支持多线程。但以现代CPU结构，不好好利用并发，和咸鱼又有什么区别呢？但是有一个尴尬的地方，C/C++运行库只能依赖系统层面进行线程的创建。所以，为了支持C运行库下的函数__threadstartex对CreateThread进行了封装，并将一些全局变量进行了封装，转换为本地变量，传入线程，这样就不会涉及到线程同步问题了。

# 4. Share

**近期要静下心来，打好基础。**温习了几种排序算法，对此有了新理解，在此做一个记录。

[三种排序算法详解：插入、冒泡、快速排序](https://blog.csdn.net/VVBBBBB/article/details/89293471)