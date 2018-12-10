# 单链表
## 什么是单链表
* 单链表是一种链式存取的数据结构，用一组任意地址空间（地址空间即存储单元）
来存放线性表的数据元素
* 数据间是以结点的形式表示（每个结点记录** 自己的数据**和**下一个节点的地址**）
* 结点由元素和指针构成（第一个结点称为**空结点**，最后一个结点称为**尾结点**）
* 头结点用来记录链表的基址，遍历链表就关注**头结点**，而尾结点指向一个**空地址NULL**，表示链表上的最后一个结点

![text](https://i.loli.net/2018/12/10/5c0e3b4f37789.png)
## 单链表反转问题

```

Reverse a singly linked list.

Example:

Input: 1->2->3->4->5->NULL
Output: 5->4->3->2->1->NULL
Follow up:

A linked list can be reversed either iteratively or recursively. Could you implement both?

```
## 解题思路

通过自行分析和查相关学习资料总结此问题可由两种思考方法去解决

* 迭代法：将头结点地址指向尾结点NULL，并将下一个节点向前提一位作为新的头结点，依次遍历整个单链表

* 递归法：每次都把下一个节点作为头结点，不断的调用自己，直到将‘’头结点‘’指向NULL

```

# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def reverseList(self, head):
        """
        :type head: ListNode
        :rtype: ListNode
        """
        if head is None:
            return None
   ## 该题给出的第一个数据即为头结点
      按照递归的思想,如果头结点为None,则满足递归条件递归##
        if head.next is None:
            p = head
        else:
            s = Solution() ##调用类
  ## 调用自身的反转函数,将头结点后数据当成一个完成的单链表处理
            p = s.reverseList(head.next)
  ## 将下一结点的指针地址数据作为头结点 
            head.next.next = head
  ## 将自身设为NULL
            head.next = None
        return p
```
