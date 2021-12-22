# 查找数组列表长度/大小的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-find-the-length-size-of-a-ArrayList/](https://www.geeksforgeeks.org/java-program-to-find-the-length-size-of-an-arraylist/)

给定一个 Java 中的数组列表，任务是编写一个 Java 程序来找到数组列表的长度或大小。

**示例:**

```java
Input: ArrayList: [1, 2, 3, 4, 5]
Output: 5

Input: ArrayList: [geeks, for, geeks]
Output: 3
```

**数组列表–**一个[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)是集合框架的一部分，存在于 **java.util** 包中。它为我们提供了 Java 中的动态数组。然而，它可能比标准数组慢，但在需要对数组进行大量操作的程序中会很有帮助。

### 方法–使用大小()方法

借助 size()方法，可以很容易地确定数组列表的大小。此方法不接受任何参数，并返回一个整数值，即数组列表的大小。

**语法:**

```java
int size = ArrayList.size();
```

下面是上述方法的实现:

**示例 1–确定整数数组列表大小的 Java 程序**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to find the size
// of an ArrayList

import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws Exception
    {

        // Creating object of ArrayList<Integer>
        ArrayList<Integer>
            arrlist = new ArrayList<Integer>();

        // Populating arrlist
        arrlist.add(1);
        arrlist.add(2);
        arrlist.add(3);
        arrlist.add(4);
        arrlist.add(5);

        // print arrlist
        System.out.println("ArrayList: "
                           + arrlist);

        // getting total size of arrlist
        // using size() method
        int size = arrlist.size();

        // print the size of arrlist
        System.out.println("Size of ArrayList = "
                           + size);
    }
}
```

**Output**

```java
ArrayList: [1, 2, 3, 4, 5]
Size of ArrayList = 5
```

**示例 2–确定字符串数组列表大小的 Java 程序**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to find the size
// of an String ArrayList

import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws Exception
    {

        // Creating object of ArrayList<Integer>
        ArrayList<String>
            arrlist = new ArrayList<String>();

        // Populating arrlist
        arrlist.add("GeeksforGeeks");
        arrlist.add("a");
          arrlist.add("computer");
        arrlist.add("science");
          arrlist.add("portal");
        arrlist.add("for");
          arrlist.add("geeks");

        // print arrlist
        System.out.println("ArrayList: "
                           + arrlist);

        // getting total size of arrlist
        // using size() method
        int size = arrlist.size();

        // print the size of arrlist
        System.out.println("Size of ArrayList = "
                           + size);
    }
}
```

**Output**

```java
ArrayList: [GeeksforGeeks, a, computer, science, portal, for, geeks]
Size of ArrayList = 7
```