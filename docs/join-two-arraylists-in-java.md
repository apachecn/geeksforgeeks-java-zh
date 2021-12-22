# 在 Java 中加入两个数组列表

> 原文:[https://www.geeksforgeeks.org/join-two-arraylists-in-java/](https://www.geeksforgeeks.org/join-two-arraylists-in-java/)

给定 Java 中的两个数组列表，任务是加入这些数组列表。

**示例:**

> **输入** : ArrayList1:【极客，For，ForGeeks】，ArrayList2:【极客，forgesks，一个计算机门户】
> **输出** : ArrayList:【极客，For，ForGeeks，Geeks，一个计算机门户】
> 
> **输入**:ArrayList 1:【G，e，e，k，s】，ArrayList 2:【F，o，r，G，e，e，k，s】
> **输出**:ArrayList:【G，e，e，k，s，F，o，r，G，e，e，k，s】

**方法:**可以借助 Collection.addAll()方法在 Java 中加入 ArrayLists。此方法由目标数组列表调用，另一个数组列表作为参数传递给此方法。此方法将第二个数组列表追加到第一个数组列表的末尾。

**语法:**

```java
ArrayList1.addAll(ArrayList2);
```

下面是上述方法的实现:

```java
// Java program to demonstrate
// How to sort ArrayList in descending order

import java.util.*;

public class GFG {
    public static void main(String args[])
    {

        // Get the ArrayList1
        ArrayList<String>
            list1 = new ArrayList<String>();

        // Populate the ArrayList
        list1.add("Geeks");
        list1.add("For");
        list1.add("ForGeeks");

        // Print the ArrayList 1
        System.out.println("ArrayList 1: "
                           + list1);

        // Get the ArrayList2
        ArrayList<String>
            list2 = new ArrayList<String>();

        list2.add("GeeksForGeeks");
        list2.add("A computer portal");

        // Print the ArrayList 2
        System.out.println("ArrayList 2: "
                           + list2);

        // Join the ArrayLists
        // using Collection.addAll() method
        list1.addAll(list2);

        // Print the joined ArrayList
        System.out.println("Joined ArrayLists: "
                           + list1);
    }
}
```