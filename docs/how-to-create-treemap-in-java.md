# 如何用 Java 创建树形图？

> 原文:[https://www . geesforgeks . org/how-create-tree map-in-Java/](https://www.geeksforgeeks.org/how-to-create-treemap-in-java/)

Java 中的 [**树形图**](https://www.geeksforgeeks.org/treemap-in-java/) 是用来实现[**地图界面**](https://www.geeksforgeeks.org/map-interface-java-examples/) 和 [**导航地图**](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/) 以及 [**抽象类**](https://www.geeksforgeeks.org/abstract-classes-in-java/) 。地图根据其键的自然顺序进行排序，或者通过地图创建时提供的 [**比较器**](https://www.geeksforgeeks.org/comparator-interface-java/) 进行排序，具体取决于使用的构造函数。

要创建树图，我们可以使用**地图类**或**树图类**参考。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program demonstrate how to create a TreeMap

import java.util.*;

class GFG {

    public static void main(String[] args)
    {
        // Declaring a treemap
        TreeMap<Integer, String> map;

        // Creating an empty TreeMap
        map = new TreeMap<Integer, String>();

        System.out.println("TreeMap successfully"
                           + " created");
    }
}
```

**Output**

```
TreeMap successfully created
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program demonstrate how to create and add elements
// to TreeMap

import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating an empty TreeMap using Map interface
        Map<Integer, String> map = new TreeMap<>();

        System.out.println("TreeMap successfully"
                           + " created");

        // Adding elements
        map.put(1, "Geeks");
        map.put(2, "for");
        map.put(3, "Geeks");

        // Printing TreeMap
        System.out.println("TreeMap: " + map);
    }
}
```

**Output**

```
TreeMap successfully created
TreeMap: {1=Geeks, 2=for, 3=Geeks}
```