# [206. Reverse Linked List](https://leetcode.cn/problems/reverse-linked-list/)



## 1 Problem

![image-20240102191751759](D:\Learn DataStructure\LeetCode-Exercises\2023\20231102\assets\image-20240102191751759.png)

## 2 Examples

![image-20240102191820133](D:\Learn DataStructure\LeetCode-Exercises\2023\20231102\assets\image-20240102191820133.png)

## 3 Codes

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        prev = None
        curr = head
        while curr != None:
            nxt = curr.next
            curr.next = prev

            prev = curr
            curr = nxt

        return prev
```



```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        # 当前处理子链表为空
        if head == None:
            return None

        # 当前处理子链表只有一个节点
        nhead = head

        # 当前处理子链表不止一个节点
        while head.next != None:
            nhead = self.reverseList(head.next)
            head.next.next = head
            head.next = None

        return nhead
```

