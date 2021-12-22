# 如何在 Java 数组列表中添加元素？

> 原文:[https://www . geesforgeks . org/how-add-element-in-Java-ArrayList/](https://www.geeksforgeeks.org/how-to-add-element-in-java-arraylist/)

Java [**数组列表**](https://www.geeksforgeeks.org/arraylist-in-java/) 类使用动态数组来存储元素。它就像一个数组，但是没有大小限制。我们可以随时添加或删除元素。因此，它比传统阵列灵活得多。

可以使用 java.util.ArrayList 类的 **add()** 方法在 Java ArrayList 中添加元素。

**1。** [**布尔加**](https://www.geeksforgeeks.org/java-util-arraylist-add-method-java/) **(对象元素):**

作为参数传递的元素被插入到列表的末尾。

**申报:**T0】

**参数:**

该元素将被添加到列表的末尾。

**返回值:**

此方法返回布尔值 true

**例:**

```
Input:
list.add("A");
list.add("B");
list.add("C");
Output:
list=[A,B,C]

Input:
list.add(1);
list.add(2);
list.add(3);
list.add(4);
Output:
list=[1,2,3,4]
```

给定方法的实现:

## Java

T0输出

```
[1, 2, 3, 4]
```