# Java 中的 Collections synchronizedstortedmap()方法，示例

> 原文:[https://www . geesforgeks . org/collections-synchronizedstortedmap-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-synchronizedsortedmap-method-in-java-with-examples/)

**java.util.Collections** 类的 **synchronizedSortedMap()** 方法用于返回由指定排序映射支持的同步(线程安全)排序映射。为了保证串行访问，通过返回的排序图(或其视图)完成对后备排序图的所有访问是至关重要的。

**语法:**

```java
public static <K, V> SortedMapK, V>
  synchronizedSortedMap(SortedMapK, V> m)
```

**参数:**该方法将排序后的**地图**作为参数“包裹”在同步排序后的地图中。

**返回值:**该方法返回指定排序地图的**同步视图**。

以下是说明**synchronizedstortedmap()**方法的示例

**例 1:**

```java
// Java program to demonstrate
// synchronizedSortedMap() method
// for <String, String> Value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of SortedMap<String, String>
            SortedMap<String, String>
                map = new TreeMap<String, String>();

            // populate the map
            map.put("1", "A");
            map.put("2", "B");
            map.put("3", "C");

            // printing the Collection
            System.out.println("Sorted Map : " + map);

            // create a sorted map
            SortedMap<String, String>
                sortedmap = Collections
                                .synchronizedSortedMap(map);

            // printing the map
            System.out.println("Synchronized sorted map is :"
                               + sortedmap);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Sorted Map : {1=A, 2=B, 3=C}
Synchronized sorted map is :{1=A, 2=B, 3=C}

```

**例 2:**

```java
// Java program to demonstrate
// synchronizedSortedMap() method
// for <Integer, Boolean> Value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of SortedMap<Integer, Boolean>
            SortedMap<Integer, Boolean>
                map = new TreeMap<Integer, Boolean>();

            // populate the map
            map.put(100, true);
            map.put(200, true);
            map.put(300, true);

            // printing the Collection
            System.out.println("Sorted Map : " + map);

            // create a sorted map
            SortedMap<Integer, Boolean>
                sortedmap = Collections
                                .synchronizedSortedMap(map);

            // printing the map
            System.out.println("Synchronized sorted map is :"
                               + sortedmap);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Sorted Map : {100=true, 200=true, 300=true}
Synchronized sorted map is :{100=true, 200=true, 300=true}

```