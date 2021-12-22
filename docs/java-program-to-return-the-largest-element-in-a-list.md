# 返回列表中最大元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序返回列表中最大的元素/](https://www.geeksforgeeks.org/java-program-to-return-the-largest-element-in-a-list/)

给定一个[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)，找到其中最大的元素。有多种方法可以解决这个问题，比如遍历列表或者使用各种内置函数。

```
Input  : List = [5, 3, 234, 114, 154]
Output : 234

Input  : List = {10, 20, 4}
Output : 20
```

**方法 1:使用 ForEach Loop**

1.  Create a List object and store multiple elements in it.
2.  Create a variable and initialize it with integer. Maximum value.
3.  Start iterating over the elements in the list for each loop, and compare each element with the variable.
4.  If the current element is greater than the variable , the variable is updated.
5.  At the end of the iteration, print the variables.

下面是上述方法的实现:

## Java

T0T7**输出**

```
The maximum value is 1540
```