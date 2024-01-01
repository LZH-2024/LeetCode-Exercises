# 242 Valid Anagram

## 1、Problem

![image-20240101222335979](D:\Learn DataStructure\LeetCode-Exercises\2024\20240101\assets\image-20240101222335979.png)

## 2、Examples

![image-20240101222355860](D:\Learn DataStructure\LeetCode-Exercises\2024\20240101\assets\image-20240101222355860.png)

## 3、Codes

```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s) != len(t):  # 若两字符串长度不同，必然false
            return False

        countS,countT = {},{}

        # 使用两个hash table记录每个字符串中各字符出现的次数
        # 两个字符串长度相同，一次循环即可
        for i in range(len(s)): 
            countS[s[i]] = 1 + countS.get(s[i],0)
            countT[t[i]] = 1 + countT.get(t[i],0)

        # 由于两字符串长度相等，仅选择一个字符串遍历判断即可
        # 只要有一个字符个数不相符合，必然false；若全相符，必然true
        for c in countS:
            if countS[c] != countT.get(c,0):
                return False
        
        return True
```

