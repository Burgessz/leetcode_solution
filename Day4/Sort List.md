# 链表排序
## 题目概述

```

Sort a linked list in O(n log n) time using constant space complexity.

Example 1:

Input: 4->2->1->3
Output: 1->2->3->4
Example 2:

Input: -1->5->3->4->0
Output: -1->0->3->4->5

```
## 解题思路
* 插入排序法：是一种简单直观的排序算法。
它的工作原理是通过构建有序序列，对于未排序数据，
在已排序序列中从后向前扫描，找到相应位置并插入。
插入排序在实现上，在从后向前扫描过程中，
需要反复把已排序元素逐步向后挪位，为最新元素提供插入空间。

```

def insert_sort(list):
    # 从第二个位置，即下标为1的元素开始向前插入
    for i in range(1, len(list)):
    # 从第i个元素开始向前比较，如果小于前一个元素，交换位置
        for j in range(i, 0, -1):
            if list[j] < list[j-1]:
                list[j], list[j-1] = list[j-1], list[j]

list = [-1,5,3,4,0]
insert_sort(list)
print(list)

```

* 快速排序：又称划分交换排序，通过一趟排序将要排序的数据分割成独立的两部分，其中一部分的所有数据都比另外一部分的所有数据都要小，然后再按此方法对这两部分数据分别进行快速排序，整个排序过程可以递归进行，以此达到整个数据变成有序序列。

   步骤为：

         1.从数列中挑出一个元素，称为"基准"

         2.重新排序数列，所有元素比基准值小的摆放在基准前面，所有元素比基准值大的摆在基准的后面（相同的数可以到任一边）。在这个分区结束之后，该基准就处于数列的中间位置。这个称为分区（partition）操作。

         3.递归地（recursive）把小于基准值元素的子数列和大于基准值元素的子数列排序。

* 递归的最底部情形，是数列的大小是零或一，也就是永远都已经被排序好了。虽然一直递归下去，但是这个算法总会结束，因为在每次的迭代（iteration）中，它至少会把一个元素摆到它最后的位置去。

```
def quick_sort(list, head, end):

    # 递归的退出条件
    if head >= end:
        return

    # 设定起始元素为要寻找位置的基准元素
    mid = list[head]

    # low为序列左边的由左向右移动的游标
    low = head

    # high为序列右边的由右向左移动的游标
    high = end

    while low < high:
        # 如果low与high未重合，high指向的元素不比基准元素小，则high向左移动
        while low < high and list[high] >= mid:
            high -= 1
        # 将high指向的元素放到low的位置上
        list[low] = list[high]

        # 如果low与high未重合，low指向的元素比基准元素小，则low向右移动
        while low < high and list[low] < mid:
            low += 1
        # 将low指向的元素放到high的位置上
        list[high] = list[low]

    # 退出循环后，low与high重合，此时所指位置为基准元素的正确位置
    # 将基准元素放到该位置
    list[low] = mid

    # 对基准元素左边的子序列进行快速排序
    quick_sort(list, head, low-1)

    # 对基准元素右边的子序列进行快速排序
    quick_sort(list, low+1, end)


list = [4,2,1,3]
quick_sort(list,0,len(list)-1)
print(list)

```
