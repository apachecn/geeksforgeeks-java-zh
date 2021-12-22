# 爪哇矢量上的二分搜索法

> 原文:[https://www.geeksforgeeks.org/binary-search-on-java-vector/](https://www.geeksforgeeks.org/binary-search-on-java-vector/)

**Vector** 是 Java 中的遗留类，从 Java 1.2 版本开始出现。实现了[收藏框架](https://www.geeksforgeeks.org/collections-in-java-2/)的[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)界面，在 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中可以找到。 [Vector](https://www.geeksforgeeks.org/java-util-vector-class-java/) 就像一个可以动态生长的数组。向量是同步的，即向量是线程安全的。向量主要用于线程同步至关重要的地方。在其他情况下，[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)表现更好。因为向量是 Java 中的遗留类，所以向量中的元素只能通过枚举来迭代。在本文中，我们将看到向量上的二分搜索法运算。[二分搜索法](https://www.geeksforgeeks.org/binary-search-in-java/)是一种搜索技术，在这种技术中，排序后的数组被重复分成两半，并检查中间元素的目标元素。要搜索向量中的目标元素，我们将使用 [Collections 类](https://www.geeksforgeeks.org/collections-class-in-java/)的[*binary search()*](https://www.geeksforgeeks.org/collections-binarysearch-java-examples/)*方法*。

![](img/72f5f3945649ffc31469290af58ac42b.png)

**语法:**

```java
binarySearch(List list, Object target)
```

**参数:**

*   要对其执行二分搜索法操作的列表类型对象。
*   目标元素的值。

**返回值:**如果找到则返回目标元素的**索引**，否则返回 **-1** 。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Demonstrate Binary Search on Vector

// Importing utility classes
import java.util.*;

// Main class
// BinarySearchOnVector
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a Vector by
        // declaring integer object of Vector class
        Vector<Integer> v = new Vector<>();

        // Adding elements to Vector
        // using add() method
        v.add(10);
        v.add(50);
        v.add(20);
        v.add(40);
        v.add(25);

        // Note: Binary search works only on sorted list

        // Sorting the above vector
        // using sort() method of Collections class
        Collections.sort(v);

        // Searching an element using binarySearch() method
        // of Collections class
        int index = Collections.binarySearch(v, 25);

        // Printing the position of the target
        System.out.println("Element is found at index : "
                           + index);
    }
}
```

**Output**

```java
Element is found at index : 2
```

**输出说明:**矢量元素未按排序顺序添加。由于二分搜索法只在排序列表中工作，我们首先对向量进行排序，然后执行二分搜索法运算。目标在索引 **2** 处找到，因此返回并打印该值。

> 时间复杂度: **O(log n)** 其中‘n’是向量的大小。

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Demonstrate Binary Search on Vector

// Importing required classes
import java.util.*;

// Main class
// BinarySearchVector
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating a Vector by
        // declaring object of Vector class of string type
        Vector<String> v = new Vector<>();

        // Adding elements to Vector
        // using add() method
        v.add("10");
        v.add("B");
        v.add("20");
        v.add("A");
        v.add("25");

        // Note: Binary search works only on sorted list

        // Sorting the above vector elements using
        // sort() of Collections class
        Collections.sort(v);

        // Printing the sorted elements of above vector
        System.out.println("Sorted Vector: " + v);

        // Searching an element using binarySearch method
        // of Collections class
        int index = Collections.binarySearch(v, "25");

        // Printing the position of target on console
        System.out.println("Element is found at index : "
                           + index);
    }
}
```

**Output**

```java
Sorted Vector: [10, 20, 25, A, B]
Element is found at index : 2
```

**输出说明:**数字串位于字母串之前。现在，目标字符串 25 位于索引 2 处，因此返回并打印该值。

> **时间复杂度:** O(log n)其中‘n’**是向量的大小。**