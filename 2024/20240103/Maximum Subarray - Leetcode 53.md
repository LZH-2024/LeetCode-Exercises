# [53. Maximum Subarray](https://leetcode.cn/problems/maximum-subarray/)



## 1 Problem

![image-20240103234226987](D:\Learn DataStructure\LeetCode-Exercises\2024\20240103\assets\image-20240103234226987.png)

## 2 Examples

![image-20240103234237980](D:\Learn DataStructure\LeetCode-Exercises\2024\20240103\assets\image-20240103234237980.png)

## 3 Codes

```python
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        maxSum = nums[0]

        # currSum表示当前数字之前的所有和
        # 根据题目要求可以发现，任何前缀和为负数的前缀序列都是不需要的，当出现这种情况时立即从当前数字开始往后寻找连续数组
        currSum = 0

        for n in nums:
            if currSum < 0:
                currSum = 0
            currSum += n
            maxSum = max(currSum,maxSum)

        return maxSum
```

