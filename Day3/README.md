# 二叉树

## 什么是二叉树

* 满足一个**根节点**最多有两个**子节点**的数据结构
* 两种比较特殊的结构形式**满二叉树**和**完全二叉树**
* 满二叉树：每个根节点都有两个子节点，直到满足需求最底层节点个数最大
* 完全二叉树：除了最后一层子节点靠左排列，其他层节点个数达到最大
### 存储方式
* 链式存储法：通过链表的形式进行存储数据，每个节点由**数据域**、**左指针域**、**右指针域*
* 顺序存储法：定义根节点所在下标位置为1，其左子节点为2，右指节点为3，依次类推
## 二叉树的遍历
* 层次遍历：类似顺序存储法的形式将数据取出，根节点>-左子节点>-右子节点

![text](https://github.com/Burgessz/leetcode_solution/blob/master/Day2/层次遍历.jpg)

* 前序遍历：根节点>-左子树>-右子树

![text](https://github.com/Burgessz/leetcode_solution/blob/master/Day2/前序.jpg)

* 中序遍历：左子树>-根节点>-右子树

![text](https://github.com/Burgessz/leetcode_solution/blob/master/Day2/中序.jpg)

* 后序遍历：左子树>-右子树>-根节点

![text](https://github.com/Burgessz/leetcode_solution/blob/master/Day2/后序.jpg)

## Binary Tree Level Order Traversal

```

Given a binary tree, return the level order traversal of its nodes' values. (ie, from left to right, level by level).

For example:
Given binary tree [3,9,20,null,null,15,7],
    3
   / \
  9  20
    /  \
   15   7
return its level order traversal as:
[
  [3],
  [9,20],
  [15,7]
]

```
### 解题思路

分析题意之后，首先想到的就是通过队列实现广度优先算法

```

def levelOrder(self, root):
        if not root:
            return []
        curr = [root]
        next = []
        bt = []
        while currLevel:
            bt.append(list(x.val for x in curr))
            for node in curr:
                if node.left:
                    next.append(node.left)
                if node.right:
                    next.append(node.right)
            curr, next = nextLevel, []
        return bt

```

