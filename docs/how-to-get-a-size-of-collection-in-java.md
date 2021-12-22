# 如何在 Java 中获取一个大小的集合？

> 原文:[https://www . geesforgeks . org/如何获取 java 大小的集合/](https://www.geeksforgeeks.org/how-to-get-a-size-of-collection-in-java/)

给定一个 Java 中的集合，任务是找到集合的长度或大小。

**示例:**

```
Input: Array_List: [1, 2, 3,4]
Output: 4

Input: Linked_List: [geeks, for, geeks]
Output: 3

```

不同集合的大小可以通过 **size()** 方法找到。此方法返回此集合中的元素数量。此方法不接受任何参数。

**下面是实现:**

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// size() method of collection

import java.util.*;

public class Example1 {
    public static void main(String[] args)
    {

        // Creating object of List<Integer>
        List<Integer> Array_List = new ArrayList<Integer>();

        // add elements 
        Array_List.add(1);
        Array_List.add(2);
        Array_List.add(3);
        Array_List.add(3);

        // getting total size of list
        // using size() method
        int size = Array_List.size();

        // print the size of list
        System.out.println("Size of list = " + size);

        // print list
        System.out.println("Array_List = " + Array_List);
    }
}
```

**Output**

```
Size of list = 4
Array_List = [1, 2, 3, 3]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// size() method of Collection
import java.util.*;
import java.io.*;

class Example2 {
    public static void main(String[] args)
    {

        // Creating object of LinkedList<Integer>
        LinkedList<String> al = new LinkedList<String>();

        // Populating LinkedList
        al.add("GEEKS");
        al.add("FOR");
        al.add("GEEKS");

        // getting total size of Linkedlist
        // using size() method
        int size = al.size();

        // print the size
        System.out.println("Size of the linkedlist = "
                           + size);

        // print Linkedlist
        System.out.println("Linkedlist = " + al);
    }
}
```

**Output**

```
Size of the linkedlist = 3
Linkedlist = [GEEKS, FOR, GEEKS]
```