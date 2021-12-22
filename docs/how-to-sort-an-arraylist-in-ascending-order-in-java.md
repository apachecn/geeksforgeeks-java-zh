# 如何在 Java 中对数组列表进行升序排序

> 原文:[https://www . geesforgeks . org/如何在 java 中按升序对数组列表进行排序/](https://www.geeksforgeeks.org/how-to-sort-an-arraylist-in-ascending-order-in-java/)

给定一个未排序的数组列表，任务是在 Java 中以升序对这个数组列表进行排序。

**示例:**

> **输入**:未排序的数组列表:【极客，For，ForGeeks，geesforgeeks，一个计算机门户】
> **输出**:已排序的数组列表:【一个计算机门户，For，ForGeeks，geesforgeeks】
> 
> **输入**:未排序的数组列表:【极客，For，ForGeeks】
> **输出**:已排序的数组列表:【For，ForGeeks，Geeks】

**方法:**可以使用 Java 中 Collections 类的 sort()方法对数组列表进行排序。此 sort()方法将待排序的集合作为参数，并返回默认情况下按升序排序的集合。

**语法:**

```java
Collections.sort(ArrayList);
```

下面是上述方法的实现:

```java
// Java program to demonstrate
// How to sort ArrayList in ascending order

import java.util.*;

public class GFG {
    public static void main(String args[])
    {

        // Get the ArrayList
        ArrayList<String>
            list = new ArrayList<String>();

        // Populate the ArrayList
        list.add("Geeks");
        list.add("For");
        list.add("ForGeeks");
        list.add("GeeksForGeeks");
        list.add("A computer portal");

        // Print the unsorted ArrayList
        System.out.println("Unsorted ArrayList: "
                           + list);

        // Sorting ArrayList in ascending Order
        // using Collection.sort() method
        Collections.sort(list);

        // Print the sorted ArrayList
        System.out.println("Sorted ArrayList "
                           + "in Ascending order : "
                           + list);
    }
}
```

**Output:**

```java
Unsorted ArrayList: [Geeks, For, ForGeeks, GeeksForGeeks, A computer portal]
Sorted ArrayList in Ascending order : [A computer portal, For, ForGeeks, Geeks, GeeksForGeeks]

```