# [167. Two Sum II - Input Array Is Sorted](https://leetcode.cn/problems/two-sum-ii-input-array-is-sorted/)



## 1 Problem

![image-20240104234047914](D:\Learn DataStructure\LeetCode-Exercises\2024\20240104\assets\image-20240104234047914.png)

## 2 Examples

![image-20240104234102400](D:\Learn DataStructure\LeetCode-Exercises\2024\20240104\assets\image-20240104234102400.png)

## 3 Codes

```python
class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        l,r = 0, len(numbers) - 1  # 先取头尾两个数，因为已排序，不符合的话必然往某一遍移动

        while l < r:
            currSum = numbers[l] + numbers[r]

            if currSum > target:   # 大了，右边大的往左移动
                r -= 1
            elif currSum < target:  # 小了，左边小的往右移动
                l += 1
            else:  # 题目必有解
                return [l+1, r+1]
```

