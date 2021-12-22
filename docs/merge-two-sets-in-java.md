# 在 Java 中合并两个集合

> 原文:[https://www.geeksforgeeks.org/merge-two-sets-in-java/](https://www.geeksforgeeks.org/merge-two-sets-in-java/)

[集合接口](https://www.geeksforgeeks.org/set-in-java/)存在于 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中，扩展[集合接口](https://www.geeksforgeeks.org/collections-in-java-2/)是一个无序的对象集合，其中不能存储重复的值。这是一个实现数学集合的接口。此接口包含从集合接口继承的方法，并添加了限制重复元素插入的功能。有两个扩展集合实现的接口，即[排序集合](https://www.geeksforgeeks.org/sortedset-java-examples/)和[导航集合](https://www.geeksforgeeks.org/navigableset-java-examples/)。

**方法:**以下是 Java 中合并两个集合的各种方法:

1.  使用双支撑初始化
2.  使用 Set 类的 addAll()方法
    *   使用用户定义的方法
    *   在用户定义函数中使用 Java 8 流
3.  在用户定义函数中使用 Java 8 流
4.  使用流类的()和 forEach()方法
5.  用收集器使用流类的()和 flatMap()方法
6.  用收集器使用流类的 concat()方法
7.  使用 Apache 公共集合
8.  使用番石榴 iterales . concat()

**方法 1:** [使用双支撑初始化](https://www.geeksforgeeks.org/double-brace-initialization-java/)

插图:

```java
Input :  a = [1, 3, 5, 7, 9]
         b = [0, 2, 4, 6, 8]
Output : [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Demonstrate Merging of two sets in Java
// Using Double brace Initialization

// Importing required classes
import java.io.*;
import java.util.*;
import java.util.stream.*;

// Main class
public class GFG {

    // Method 1
    // To merge two sets
    // using DoubleBrace Initialisation
    public static <T> Set<T> mergeSet(Set<T> a, Set<T> b)
    {

        // Adding all elements of respective Sets
        // using addAll() method
        return new HashSet<T>() {
            {
                addAll(a);
                addAll(b);
            }
        };
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Creating the sets to be merged

        // First set
        Set<Integer> a = new HashSet<Integer>();
        // Applying Arrays.asList()
        a.addAll(
            Arrays.asList(new Integer[] { 1, 3, 5, 7, 9 }));

        // Second set
        Set<Integer> b = new HashSet<Integer>();
        // Applying Arrays.asList()
        b.addAll(
            Arrays.asList(new Integer[] { 0, 2, 4, 6, 8 }));

        // Printing the Sets
        System.out.println("Set a: " + a);
        System.out.println("Set b: " + b);

        // Calling Method 1 to merge above Sets
        System.out.println("Merged Set: " + mergeSet(a, b));
    }
}
```

**Output:** 

```java
Set a: [1, 3, 5, 7, 9]
Set b: [0, 2, 4, 6, 8]
Merged Set: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

**方法 2:** 使用集合类的 addAll()方法

addAll()方法由 Set 接口提供。它将作为参数传递的元素添加到这个集合的最后。

**2-A.** 使用用户定义的方法

插图:

```java
Input  : a = [1, 3, 5, 7, 9]
         b = [0, 2, 4, 6, 8]
Output : [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate Merging of Two Sets
// Using SetAll() method

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Method 1
    // To merge two sets
    // using addAll()
    public static <T> Set<T> mergeSet(Set<T> a, Set<T> b)
    {

        // Creating an empty HashSet
        Set<T> mergedSet = new HashSet<T>();

        // Adding the two sets to be merged
        // into the new Set using addAll() method
        mergedSet.addAll(a);
        mergedSet.addAll(b);

        // Returning the merged set
        return mergedSet;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Creating the sets to be merged

        // First Set
        Set<Integer> a = new HashSet<Integer>();
        a.addAll(
            Arrays.asList(new Integer[] { 1, 3, 5, 7, 9 }));

        // Second Set
        Set<Integer> b = new HashSet<Integer>();
        b.addAll(
            Arrays.asList(new Integer[] { 0, 2, 4, 6, 8 }));

        // Printing the Sets
        System.out.println("Set a: " + a);
        System.out.println("Set b: " + b);

        // Calling method 1 to merge above Sets
        // and printing it
        System.out.println("Merged Set: " + mergeSet(a, b));
    }
}
```

**Output:** 

```java
Set a: [1, 3, 5, 7, 9]
Set b: [0, 2, 4, 6, 8]
Merged Set: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```