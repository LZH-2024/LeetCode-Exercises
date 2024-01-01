# [143. Reorder List](https://leetcode.cn/problems/reorder-list/)

## 1 Problem

![image-20240101224120792](D:\Learn DataStructure\LeetCode-Exercises\2024\20240101\assets\image-20240101224120792.png)

## 2 Examples

![image-20240101224144601](D:\Learn DataStructure\LeetCode-Exercises\2024\20240101\assets\image-20240101224144601.png)

## 3 Codes

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reorderList(self, head: Optional[ListNode]) -> None:
        """
        Do not return anything, modify head in-place instead.
        """
		# 快慢指针，将原链表划分为两部分
        slow, fast = head, head.next
        while fast and fast.next:
            fast = fast.next.next
            slow = slow.next

        # 前后两部分分开成两个链表
        second = slow.next
        slow.next = None

        # 将后面的链表顺序反转
        pre, curr = None, second
        while curr:
            nxt = curr.next
            curr.next = pre

            pre = curr
            curr = nxt

        l1, l2 = head, pre

        # 将两个链表进行二路归并（按顺序后面的链表节点插入前面链表）
        while l2:
            l1nxt, l2nxt = l1.next, l2.next 
            l1.next = l2
            l2.next = l1nxt

            l1 = l1nxt
            l2 = l2nxt
```

