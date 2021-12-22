# 从树形图中获取排序子图的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-get-sorted-sub-map-from-tree map/](https://www.geeksforgeeks.org/java-program-to-get-sorted-sub-map-from-treemap/)

Java 中的树图是以键值和映射值对的映射方式存储元素的容器。每个元素都有一个关键的**–**值和一个相应的映射值。所有键值都是唯一的，并且任何两个映射的值都不能有相同的键值。它基于红黑树实现，在红黑树实现中，值在树映射中的插入顺序并不重要，它们仍然根据键进行排序，这与哈希映射不同。

**树形图语法:**

```java
TreeMap<Integer, String> tree_map= new TreeMap<Integer, String>();
```

**SubMap 的语法:**

**情况 1:** 方法将包括开始键但不包括结束键

```java
tree_map.submap(starting_key, ending_key);
```

**情况 2:** 要包含两个键，用键传递真

```java
tree_map.submap(starting_key, true, ending_key, true);
```

**情况 3:** 要排除任何键，用键

```java
tree_map.submap(starting_key, false, ending_key, true);
```

传递 false

**方法:**

1.  Brute force method
2.  Use predefined functions
3.  Use defined comparators.
4.  Using a user-defined comparator

**方法一:**打印默认排序子地图

T5】JavaT7

```java
// Java Program to  Get Sorted Sub-Map from TreeMap

// Importing all classes of
// java.util package
import java.util.*;

public class GFG {

    // Main driver code
    public static void main(String[] args)
    {
        // Create a TreeMap
        TreeMap<Integer, String> my_map
            = new TreeMap<Integer, String>();

        // Adding Element to TreeMap
        my_map.put(5, "DoubleAlpha");
        my_map.put(1, "Alpha");
        my_map.put(3, "Beta");
        my_map.put(2, "Gamma");
        my_map.put(4, "Theta");

        // Printing default sorted elements in given range
        // using subMap function
        System.out.println(
            "Elements:  "
            + my_map.subMap(1, true, 5, true));
    }
}
```

T8T10**输出**T1

**方法 2:** 使用预定义函数对地图进行反向排序

**例:**

## 爪哇

```java
// Java Program to  Get Sorted Sub-Map from TreeMap
// using predefined functions

// Importing all classes of
// java.util package
import java.util.*;

public class GFG {

    // Main driver code
    public static void main(String[] args)
    {
        // Create a TreeMap
        TreeMap<Integer, String> my_map
            = new TreeMap<Integer, String>();

        // Adding elements to TreeMap
        my_map.put(5, "DoubleAlpha");
        my_map.put(1, "Alpha");
        my_map.put(3, "Beta");
        my_map.put(2, "Gamma");
        my_map.put(4, "Theta");

        // Reversing elements of map in
        // descending order
        Map<Integer, String> reversed_map
            = my_map.descendingMap();

        // Printing default reverse sorted elements
        // using subMap() function
        System.out.println("Elements:  " + reversed_map);
    }
}
```

**输出**

```java
Elements:  {5=DoubleAlpha, 4=Theta, 3=Beta, 2=Gamma, 1=Alpha}
```