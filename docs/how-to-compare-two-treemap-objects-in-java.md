# 如何比较 Java 中的两个树形图对象？

> 原文:[https://www . geesforgeks . org/how-to-compare-two-tree map-objects-in-Java/](https://www.geeksforgeeks.org/how-to-compare-two-treemap-objects-in-java/)

java 中的[](https://www.geeksforgeeks.org/treemap-in-java/)**类提供了一种按排序顺序存储键值对的方法。下面的示例显示了如何使用 [**equals()**](https://www.geeksforgeeks.org/java-equals-compareto-equalsignorecase-and-compare/) 方法来比较两个树状图对象。它比较两个树映射对象，如果两个映射具有相同的映射，则返回 true，否则返回 false。**

****语法:****

```java
boolean equals(Object o)
```

****返回:**如果两个地图相等则返回真，否则返回假。**

## **Java**

```java
// Java program to Compare Two TreeMap Objects
import java.io.*;
import java.util.ArrayList;
import java.util.TreeMap;

public class GFG {

    public static void main(String[] args)
    {

        // Creating first TreeMap
        TreeMap<Integer, String> Office1
            = new TreeMap<Integer, String>();

        Office1.put(1, "Mumbai");
        Office1.put(2, "Delhi");

        // Creating second TreeMap
        TreeMap<Integer, String> Office2
            = new TreeMap<Integer, String>();

        Office2.put(1, "Mumbai");
        Office2.put(2, "Delhi");

        // equals compares two TreeMap objects and
        // returns true if both of the maps have the same
        // mappings.
        System.out.println(Office1.equals(Office2));

        // add new mapping to second TreeMap
        Office2.put(3, "Goa");

        // this will return false as both TreeMap objects do
        // not contain same mappings
        System.out.println(Office1.equals(Office2));
    }
}
```

****输出**

```java
true
false
```**