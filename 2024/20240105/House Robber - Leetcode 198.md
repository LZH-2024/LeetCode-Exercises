# [198. House Robber](https://leetcode.cn/problems/house-robber/)



## 1 Problem

![image-20240105221402008](D:\Learn DataStructure\LeetCode-Exercises\2024\20240105\assets\image-20240105221402008.png)

## 2 Examples

![image-20240105221413115](D:\Learn DataStructure\LeetCode-Exercises\2024\20240105\assets\image-20240105221413115.png)

## 3 Codes

```python
class Solution:
    def rob(self, nums: List[int]) -> int:
        rob = [0,0,0]

        for n in nums:
            # 因为不能选连续相邻的，当轮到n决策时，只有两种情况考虑：
            # 1、选择n + n前面的前面那个数决策出的结果
            # 2、选择放弃当前的n，此时最大值应同n前面那个数决策出的结果相同
            # 即 rob[i] = max(nums[i] + rob[i-2], rob[i-1])
            rob[2] = max(rob[0] + n, rob[1])
            rob[0] = rob[1]
            rob[1] = rob[2]
           
        return rob[2]
```

