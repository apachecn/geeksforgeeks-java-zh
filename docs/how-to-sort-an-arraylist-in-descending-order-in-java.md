# 如何在 Java 中对数组列表进行降序排序

> 原文:[https://www . geesforgeks . org/如何在 java 中按降序对数组列表进行排序/](https://www.geeksforgeeks.org/how-to-sort-an-arraylist-in-descending-order-in-java/)

给定一个未排序的数组列表，任务是在 Java 中以降序对这个数组列表进行排序。

**示例:**

> **输入**:未排序的数组列表:【极客，For，ForGeeks，geesforgeeks，A 计算机门户】
> **输出**:已排序的数组列表:【极客，ForGeeks，geesforgeks，For，A 计算机门户】
> 
> **输入**:未排序的数组列表:【极客，For，forgek】
> **输出**:已排序的数组列表:【极客，forgek，For】

**方法:**可以使用 Java 中 Collections 类的 sort()方法对数组列表进行排序。此 sort()方法以要排序的集合和 Collections.reverseOrder()为参数，返回按降序排序的集合。Collections.reverseOrder()在此方法中充当比较器。

**语法:**

```
Collections.sort(ArrayList, Collections.reverseOrder());
```

下面是上述方法的实现:

```
// Java program to demonstrate
// How to sort ArrayList in descending order

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

        // Sorting ArrayList in descending Order
        // using Collection.sort() method
        // by passing Collections.reverseOrder() as comparator
        Collections.sort(list, Collections.reverseOrder());

        // Print the sorted ArrayList
        System.out.println("Sorted ArrayList "
                           + "in Descending order : "
                           + list);
    }
}
```

**Output:**

```
Unsorted ArrayList: [Geeks, For, ForGeeks, GeeksForGeeks, A computer portal]
Sorted ArrayList in Descending order : [GeeksForGeeks, Geeks, ForGeeks, For, A computer portal]

```