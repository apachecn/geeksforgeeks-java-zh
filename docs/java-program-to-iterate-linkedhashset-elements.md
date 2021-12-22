# Java 程序迭代链接的 HashSet 元素

> 原文:[https://www . geesforgeks . org/Java-program-to-iterate-link edhashset-elements/](https://www.geeksforgeeks.org/java-program-to-iterate-linkedhashset-elements/)

[**链接的 HashSet**](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 是 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 的有序版本，维护所有元素的双向链表。当需要维护迭代顺序时，使用这个类。当迭代一个 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 时，顺序是不可预测的，而 LinkedHashSet 让我们按照元素插入的顺序迭代元素。当使用迭代器循环遍历 LinkedHashSet 时，元素将返回到它们被插入的顺序。

**迭代链接的不同方式 HashSet 元素:**

1.  Use for-for-each loop
2.  Using iterators
3.  Use JDK 1.8 stream

**方法 1:** 使用 for-each 循环

## Java

```
// Java Program to Iterate LinkedHashSet Elements

import java.util.*;
import java.lang.*;
import java.io.*;

class GFG {
    // Main driver method
    public static void main(String[] args)
        throws java.lang.Exception
    {
        // Creating a LinkedHashSet
        LinkedHashSet<Integer> hashSet
            = new LinkedHashSet<Integer>();

        // Adding elements to LinkedHashSet
        // Custom inputs
        hashSet.add(1);
        hashSet.add(2);
        hashSet.add(3);
        hashSet.add(4);
        hashSet.add(5);

        // Iteration over HashSet
        // using for-each loop
        for (Integer element : hashSet)

            // Print the elements of LinkedHashSet created above
            System.out.println("Element is " + element);
    }
}
```

**输出**

```
Element is 1
Element is 2
Element is 3
Element is 4
Element is 5
```