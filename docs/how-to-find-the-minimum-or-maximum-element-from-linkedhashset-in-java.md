# 如何在 Java 中从 LinkedHashSet 中找到最小或最大元素？

> 原文:[https://www . geeksforgeeks . org/如何从 java 中的 linkedhashset 找到最小或最大元素/](https://www.geeksforgeeks.org/how-to-find-the-minimum-or-maximum-element-from-linkedhashset-in-java/)

给定一个 LinkedHashSet，任务是在 Java 中从这个 [**LinkedHashSet**](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 中找到最小和最大元素。有两种方法可以从 Java 中的 LinkedHashSet 中找到最小或最大元素，如下所示

1.  **使用集合类的最小和最大方法**
2.  **通过迭代链接的哈希集**

**示例:**

```java
Input : LinkedHashset : {1, 56, 8, 24, 50}
Output: Maximum Element: 56
       Minimum Element: 1

Input : LinkedHashset : {2, 34, 100, 29, 30}
Output: Maximum Element: 100
       Minimum Element: 2
```

**方法 1:**

Collections 类的 max 和 min 方法返回指定集合对象的最大和最小元素。

*   [**collections . max(Object obj):**](https://www.geeksforgeeks.org/collections-max-method-in-java-with-examples/)**接受收藏对象。**
*   **[**collections . min(Object obj):**](https://www.geeksforgeeks.org/collections-min-method-in-java-with-examples/)**接受采集对象。****

****下面的 Java 代码使用 Collections 类的预定义的 min，max 方法从 LinkedHashSet 中查找最小和最大元素。****

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```java
**// Java Program to find the minimum or
// maximum element from LinkedHashSe
import java.io.*;
import java.util.*;

class Main {
    public static void main(String[] args)
    {

        // create a new LinkedHashSet
        LinkedHashSet<Integer> lhs
            = new LinkedHashSet<Integer>();

        // add elements to LinkedHashSet
        lhs.add(1);
        lhs.add(56);
        lhs.add(8);
        lhs.add(24);
        lhs.add(50);

        // finding maximum and minimum using inbuilt
        // functions
        int maximum = Collections.max(lhs);
        int minimum = Collections.min(lhs);

        System.out.println("Maximum element: " + maximum);
        System.out.println("Minimum element: " + minimum);
    }
}**
```

******Output**

```java
Maximum element: 56
Minimum element: 1
```**** 

******方法 2:******

****使用增强 for 循环或迭代器迭代 LinkedHashSet，并找到最大和最小元素。****

****考虑下面的 Java 代码，它通过迭代 LinkedHashSet 中的每个元素来找到最大和最小元素。****

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```java
**// Java Program to find the minimum or
// maximum element from LinkedHashSet
import java.io.*;
import java.util.*;

class Main {
    public static void main(String[] args)
    {

        // create a new LinkedHashSet
        LinkedHashSet<Integer> lhs
            = new LinkedHashSet<Integer>();

        // add elements to LinkedHashSet
        lhs.add(1);
        lhs.add(56);
        lhs.add(8);
        lhs.add(24);
        lhs.add(50);

        // Iterate over the LinkedHashSet
        int maximum = Integer.MIN_VALUE;
        int minimum = Integer.MAX_VALUE;

        for (Integer num : lhs) {
            if (maximum < num)
                maximum = num;
        }

        for (Integer num : lhs) {
            if (minimum > num)
                minimum = num;
        }

        System.out.println("Maximum element: " + maximum);
        System.out.println("Minimum element: " + minimum);
    }
}**
```

******Output**

```java
Maximum element: 56
Minimum element: 1
```****