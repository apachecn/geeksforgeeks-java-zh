# 如何在 Java 地图中找到键最大的条目

> 原文:[https://www . geesforgeks . org/如何找到 java 地图中最大键的条目/](https://www.geeksforgeeks.org/how-to-find-the-entry-with-largest-key-in-a-java-map/)

给定一个 Java 中的[地图](https://www.geeksforgeeks.org/map-interface-java-examples/)，任务是找出这个地图中关键字最高的条目。

**示例:**

```java
Input: Map = {ABC = 10, DEF = 30, XYZ = 20}
Output: XYZ = 20

Input: Map = {1 = 40, 2 = 30, 3 = 60}
Output: 3 = 60

```

**接近**

1.  [逐条目迭代地图条目](https://www.geeksforgeeks.org/iterate-map-java/)

    ```java
    for (Map.Entry entry : map.entrySet()) 
    {
        // Operations
    } 
    ```

2.  将第一个条目存储在引用变量中，以便最初进行比较。
3.  如果当前条目的键大于引用条目的值，则将当前条目存储为引用条目。
4.  对地图中的所有条目重复此过程。
5.  最后，引用变量具有映射中最高键的必需条目。
6.  打印此条目

下面是上述方法的实现:

```java
// Java program to find entry
// with highest key in a map

import java.util.*;

public class GFG {

    // Find the entry with highest key
    public static <K extends Comparable<K>, V> Map.Entry<K, V>
    getMaxEntryInMapBasedOnKey(Map<K, V> map)
    {
        // To store the result
        Map.Entry<K, V> entryWithMaxKey = null;

        // Iterate in the map to find the required entry
        for (Map.Entry<K, V> currentEntry : map.entrySet()) {

            if (

                // If this is the first entry,
                // set the result as this
                entryWithMaxKey == null

                // If this entry's key is more than the max key
                // Set this entry as the max
                || currentEntry.getKey()
                           .compareTo(entryWithMaxKey.getKey())
                       > 0) {

                entryWithMaxKey = currentEntry;
            }
        }

        // Return the entry with highest key
        return entryWithMaxKey;
    }

    // Print the map
    public static void print(Map<String, Integer> map)
    {

        System.out.print("Map: ");

        // If map does not contain any value
        if (map.isEmpty()) {
            System.out.println("[]");
        }

        else {
            System.out.println(map);
        }
    }

    // Driver code
    public static void main(String[] args)
    {

        Map<String, Integer> map
            = new HashMap<>();
        map.put("ABC", 10);
        map.put("DEF", 30);
        map.put("XYZ", 20);

        print(map);

        System.out.println(
            "Entry with highest key: "
            + getMaxEntryInMapBasedOnKey(map));
    }
}
```

**Output:**

```java
Map: {ABC=10, DEF=30, XYZ=20}
Entry with highest key: XYZ=20

```