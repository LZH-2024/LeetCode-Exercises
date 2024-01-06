# [21. Merge Two Sorted Lists](https://leetcode.cn/problems/merge-two-sorted-lists/)



## 1 Problem

![image-20240106232624879](D:\Learn DataStructure\LeetCode-Exercises\2024\20240106\assets\image-20240106232624879.png)

## 2 Examples

![image-20240106232639018](D:\Learn DataStructure\LeetCode-Exercises\2024\20240106\assets\image-20240106232639018.png)

## 3 Codes

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:

        dummy = ListNode()
        tail = dummy

        while list1 and list2:
            if list1.val <= list2.val:
                tail.next = list1
                list1 = list1.next
            else:
                tail.next = list2
                list2 = list2.next

            tail = tail.next

        if list1 == None:
            tail.next = list2
        if list2 == None:
            tail.next = list1

        return dummy.next;
```

