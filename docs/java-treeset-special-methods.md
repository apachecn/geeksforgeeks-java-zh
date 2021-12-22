# Java TreeSet 特殊方法

> 原文:[https://www.geeksforgeeks.org/java-treeset-special-methods/](https://www.geeksforgeeks.org/java-treeset-special-methods/)

TreeSet 是 Java 中 **SortedSet** 接口最重要的实现之一，它使用**树**进行存储。TreeSet 通过继承**抽象集**类实现了一个**导航集**接口。这意味着存储在树集中的元素是有序的，即以升序。由于 TreeSet 的这一特性，除了传统上由 Collection 接口提供的方法之外，它还提供了某些令人惊叹的 NavigableSet 接口方法。

> **注:**由于 TreeSet 是 Set 的实现，因此不允许元素重复。

TreeSet 提供的一些具体方法如下:

1.  *Floor ()* Method

*下()*

3.  Ceiling () method
4.  T14] Higher () method
5.  T18] Subset () method

6.  【T26】tailSet()方法

现在让我们讨论所有方法及其实现，如下所示

**方法 1:**T2【楼层()方法

此方法返回集合中小于或等于给定元素的最大元素，如果没有这样的元素，则返回 null。

**参数:**需要搜索小于或等于值的数字

**语法:**

```java
treeSetObject.floor(argument) ;
```

**示例:**

## Java

```java
// Java Program to demonstrate Floor Method in TreeSet

// Importing input output classes
import java.io.*;
// Importing TreeSet and Set classes from java.util package
import java.util.Set;
import java.util.TreeSet;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of TreeSet of Integer type
        // Initializing object with integer values using
        // Set.of() method
        TreeSet<Integer> treeSet
            = new TreeSet<>(Set.of(12, 98, 54, 37, 68));

        // Print and display elements in object
        System.out.println("Tree set = " + treeSet);

        // Case 1

        // Using floor() method over treeSet elements but
        // note floor() method is inclusive of the limit
        // Hence maximum element is returned
        System.out.println("floor(60) = "
                           + treeSet.floor(60));

        // Case 2

        // Using floor() method over treeSet elements,
        // therefore output of the below line will be the
        // number itself
        System.out.println("floor(54) = "
                           + treeSet.floor(54));
    }
}
```

**输出**

```java
Tree set = [12, 37, 54, 68, 98]
floor(60) = 54
floor(54) = 54
```

**方法二:** *下()*方法

此方法返回该集合中严格小于给定元素的最大元素，如果没有这样的元素，则返回 null。

**参数:**需要找到小于值的数字。

**语法:**

```java
treeSetObject.lower(argument) ;
```

**示例:**

## Java

```java
// Java Program to demonstrate Lower Method in TreeSet

// Importing input output classes
import java.io.*;
// Importing TreeSet and Set classes from java.util package
import java.util.Set;
import java.util.TreeSet;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of TreeSet of Integer type
        // Initializing object with integer values using
        // Set.of() method
        TreeSet<Integer> treeSet
            = new TreeSet<>(Set.of(12, 98, 54, 37, 68));

        // Print and display elements in object
        System.out.println(treeSet);

        // Case 1
        // Using lower() method ober treeSet elements where
        // argument passed is greater then max elememnt in
        // TreeSet therefore returning max element itself
        System.out.println("lower(90) = "
                           + treeSet.lower(90));

        // Case 2
        // Using lower() method ober treeSet elements where
        // argument passed is not greater then max elememnt
        // in TreeSet therefore returning element lesser
        // than that passed as an argumennt
        System.out.println("lower(68) = "
                           + treeSet.lower(68));

        // Also note that lower() method is exclusive of the
        // limit
    }
}
```

**输出**

```java
[12, 37, 54, 68, 98]
lower(90) = 68
lower(68) = 54
```

**方法三:** *天花板()*方法

此方法返回该集合中大于或等于给定元素的最少元素，如果没有这样的元素，则返回 null。

**参数:**需要找到小于或等于值的数。

**语法:**

```java
treeSetObject.lower(argument) ;
```

示例:

## 爪哇

T0输出

```java
tree set = [12, 37, 54, 68, 98]
ceiling(50) = 54
ceiling(68) = 68
ceiling(100) = null
```