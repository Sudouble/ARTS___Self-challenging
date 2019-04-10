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

# 3. Tips

# 4. Share

