# 用指定值初始化单行列表

> 原文:[https://www . geesforgeks . org/initialize-a-in-a-list-in-single-line-with-specific-value/](https://www.geeksforgeeks.org/initialize-a-list-in-a-single-line-with-a-specified-value/)

给定一个值 **N** ，任务是仅使用 Collection Framework 在 [Java](https://www.geeksforgeeks.org/java-tutorials/) 中的一行中创建一个具有该值 N 的[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)。

**示例:**

```java
Input: N = 5
Output: [5]

Input: N = GeeksForGeeks
Output: [GeeksForGeeks]

```

**进场:**

*   获取值 N
*   使用[collections . N copes()方法](https://www.geeksforgeeks.org/collections-ncopies-java/)生成单值为 N 的集合
*   将此收藏存储为列表。

下面是上述方法的实现:

```java
// Java program to initialize a list in a single
// line with a specified value
// using Collection Framework only

import java.io.*;
import java.util.*;
import java.util.stream.*;

class GFG {

    // Function to create a List
    // with the specified value
    public static <T> List<T> createList(T N)
    {

        // Currently only one value is taken
        int size = 1;

        // Generate a Collection with a single value N
        List<T> list = Collections.nCopies(size, N);

        return list;
    }

    // Driver code
    public static void main(String[] args)
    {

        int N = 1024;
        System.out.println("List with element "
                           + N + ": "
                           + createList(N));

        String str = "GeeksForGeeks";
        System.out.println("List with element "
                           + str + ": "
                           + createList(str));
    }
}
```

**Output:**

```java
List with element 1024: [1024]
List with element GeeksForGeeks: [GeeksForGeeks]

```