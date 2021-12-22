# Java 中 TreeMap 和 TreeSet 的区别

> 原文:[https://www . geesforgeks . org/tree map-and-treeset-in-Java/](https://www.geeksforgeeks.org/difference-between-treemap-and-treeset-in-java/)的区别

[**TreeSet**](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 主要是 java 中 SortedSet 的一个实现，不允许重复，对象以排序和升序的方式存储。

*树集的一些重要特征是:*

*   在树集中不允许重复值，因为它实现了 [<u>排序集</u>](https://www.geeksforgeeks.org/sortedset-java-examples/) 界面。
*   树集中的对象以升序存储。
*   在 TreeSet 中，元素的插入顺序不保持不变。

[**树状图**](https://www.geeksforgeeks.org/treemap-in-java/)**是地图界面的一个实现。TreeMap 也是 NavigableMap 和 AbstractMap 类的实现。**

***树形图的一些重要特征是:***

*   **在树形图中，空键(如 Map)是不允许的，因此抛出 [<u>空指针异常</u>](https://www.geeksforgeeks.org/null-pointer-exception-in-java/) (多个空值可能与不同的键相关联)。**
*   **树形图不支持 [<u>Entry.setValue</u>](https://www.geeksforgeeks.org/map-entry-interface-java-example/) 方法。**

**下面是 Java 中的 TreeSet 和 TreeMap 的图示:**

****例 1:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Illustration of TreeMap and TreeSet in Java
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        TreeSet<Integer> set = new TreeSet<>();
        set.add(3);
        set.add(4);
        set.add(3);
        set.add(5);

        TreeMap<Integer, Integer> tm = new TreeMap<>();
        tm.put(2, 4);
        tm.put(3, 5);
        tm.put(4, 5);
        tm.put(2, 3);
        System.out.println(set);
        System.out.println(tm);
    }
}
```

****Output**

```
[3, 4, 5]
{2=3, 3=5, 4=5}
```** 

****例 2:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Illustration of TreeMap and TreeSet in Java
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        TreeSet<String> l = new TreeSet<>();
        l.add("geeks");
        l.add("FOR");
        l.add("geeks");
        l.add("tutorial");

        TreeMap<Integer, String> l1 = new TreeMap<>();

        l1.put(1, "geeks");
        l1.put(2, "FOR");
        l1.put(3, "geeks");
        l1.put(4, "tutorial");
        System.out.println(l);
        System.out.println(l1);
    }
}
```

****Output**

```
[FOR, geeks, tutorial]
{1=geeks, 2=FOR, 3=geeks, 4=tutorial}
```** 

<figure class="table">

| 南号码 | 

**TreeSet**

 | 

**树图**

 |
| --- | --- | --- |
| 1. | TreeSet 在 Java 中实现了 SortedSet。 | 树形地图在 Java 中实现地图接口 |
| 2. | TreeSet 在 java 中存储了一个对象。 | 树映射存储两个对象一个键和一个值。 |
| 3. | TreeSet 不允许在 java 中复制对象。 | java 中的 TreeMap 允许重复值。 |
| 4. | TreeSet 在 Java 中实现了 NavigableSet。 | TreeMap 在 Java 中实现了 NavigableMap。 |
| 5. | TreeSet 基于对象进行排序。 | 树形图是根据关键字排序的。 |

</figure>