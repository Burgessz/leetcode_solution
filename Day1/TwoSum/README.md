# leetcode_solution

## Description 

### 1.Two Sum

---------------------------------------------------------------

Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

```

Example:

Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].

```
## Solution
* Approach 1: Brute Force 

The brute force approach is simple. Loop through each element xx and find if there is another value that equals to target - xtarget−x.

这是能最先想到的方法，通过遍历整个数组查找出符合要求的元素

* 时间复杂度：O（n^2）

* 空间复杂度：O（1）

*Approach 2:  Hash Table

这种方法是通过建立散列表即字典的形式，将数组按key,value的方式存储在字典里，只需遍历一次列表，通过查找字典中是否有等于target-num为止

### 提交结果

![text](https://i.loli.net/2018/12/09/5c0cd19b2e229.png)

## Hash

![text](https://i.loli.net/2018/12/09/5c0cdb7d4faa1.png)
