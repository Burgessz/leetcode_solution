# 递归
## 什么是递归？

程序调用自身的编程技巧称为递归（ recursion），用通俗的理解就是
将一个复杂的问题层层转化为一个与原问题相似的较小规模的问题
进行求解，通过对问题的层层分析，最终找到通用的解题思想，递归策略
只需要少量的程序重复多次计算，就可以减少程序的代码量。
用有限的语句来定义对象的无限集。

### 递归算法应用的三类问题

* 数据的定义是按递归定义的（斐波那契数列）

* 问题解法按递归算法实现的（回溯）

* 数据的结构形式是按递归定义的（树的遍历，图的搜索）

#### 举例：斐波那契数列

* 斐波那契数列定义是指类似于1,1,2,3,5,8,13,21,34,55,89...
从第三个元素开始，每个数值都等于前两个数值的和

* 在生活中类似于斐波那契这样的例子有很多，最经典的问题有：兔子繁殖问题、爬楼梯问题

* 自然界中好多现象都遵循斐波那契规律，例如：向日葵的内条纹，树枝叉的生长，正是因为
斐波那契是堆积最有效的方式，所以自然界生物选择此类方式生长，更有趣的是，前后每两个数的
比值都趋近于**0.618**，这个数值就是黄金分割点的比例值，多么有趣值得探究的问题
```
def fibonacci(self,n):
    if n==0 and n==1:
        return 1
    else :
        return fibonacci(n-1) + fibonacci(n-2)
```
## Pow(x, n)

```
Implement pow(x, n), which calculates x raised to the power n (xn).

Example 1:

Input: 2.00000, 10
Output: 1024.00000
Example 2:

Input: 2.10000, 3
Output: 9.26100
Example 3:

Input: 2.00000, -2
Output: 0.25000
Explanation: 2-2 = 1/22 = 1/4 = 0.25
Note:

-100.0 < x < 100.0
n is a 32-bit signed integer, within the range [−231, 231 − 1]

```
### 解题思路
* 这是经典的递归问题，此题共分为三种情况考虑**n=negetive**;**n=even**;**n==odd**

* 注意：为了避免内存溢出导致的超时，采用分治思想，将N分为2/n,2/n（n=even） 

```
class Solution:
    def myPow(self, x, n):
        """
        :type x: float
        :type n: int
        :rtype: float
        """
        if n ==0 and n == 1:
            return 1

        else :
            return x**n
            
 class Solution:
    def myPow(self, x, n):
        """
        :type x: float
        :type n: int
        :rtype: float
        """
        if n ==0 and n == 1:
            return 1
        if not n:
            return 1
        if n < 0:
            return 1.0 / self.myPow(x, -n)
        if n%2 == 0: 
            result = self.myPow(x, n / 2)
            return result * result
        else: 
            return x * self.myPow(x, n-1)
            
 ```

![text](https://i.loli.net/2018/12/13/5c1230e567f93.png)

![text](https://i.loli.net/2018/12/13/5c1230e56aa41.png)
