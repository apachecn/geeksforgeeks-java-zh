# 使用 forEach 循环展平 Java 中的地图流

> 原文:[https://www . geesforgeks . org/flat-a-stream-of-map-in-Java-using-foreach-loop/](https://www.geeksforgeeks.org/flatten-a-stream-of-map-in-java-using-foreach-loop/)

给定一个 Java 中的映射流，任务是使用 forEach()方法展平该流。

**示例:**

```java
Input: map = {1=[1, 2], 2=[3, 4, 5, 6], 3=[7, 8, 9]}
Output: [1, 2, 3, 4, 5, 6, 7, 8, 9]

Input: map = {1=[G, e, e, k, s], 2=[F, o, r], 3=[G, e, e, k, s]}
Output: [G, e, e, k, s, F, o, r]

```

**进场:**

1.  获取要展平的地图。
2.  创建一个空列表来收集展平的元素。
3.  在 forEach 循环的帮助下，将地图值的每个元素转换为流，并将其添加到列表中
4.  该列表是必需的展平地图。

下面是上述方法的实现:

**示例 1:** 使用整数列表。

```java
// Java program to flatten a stream of map
// using forEach() method

import java.util.*;
import java.util.stream.*;

class GFG {

    // Function to flatten a Stream of Map
    public static <T> List<T> flattenStream(Collection<List<T> > lists)
    {

        // Create an empty list to collect the stream
        List<T> finalList = new ArrayList<>();

        // Using forEach loop
        // convert each list into stream
        // and add the stream into list
        for (List<T> list : lists) {
            list.stream()
                .forEach(finalList::add);
        }

        // Return the final flattened list
        return finalList;
    }

    public static void main(String[] args)
    {

        // Get the map to be flattened.
        Map<Integer, List<Integer> > map = new HashMap<>();
        map.put(1, Arrays.asList(1, 2));
        map.put(2, Arrays.asList(3, 4, 5, 6));
        map.put(3, Arrays.asList(7, 8, 9));

        // Flatten the Stream
        List<Integer> flatList = flattenStream(map.values());

        // Print the flattened list
        System.out.println(flatList);
    }
}
```

**Output:**

```java
[1, 2, 3, 4, 5, 6, 7, 8, 9]

```

**示例 2:** 使用字符列表。

```java
// Java program to flatten a stream of map
// using forEach() method

import java.util.*;
import java.util.stream.*;

class GFG {

    // Function to flatten a Stream of Map
    public static <T> List<T> flattenStream(Collection<List<T> > lists)
    {

        // Create an empty list to collect the stream
        List<T> finalList = new ArrayList<>();

        // Using forEach loop
        // convert each list into stream
        // and add the stream into list
        for (List<T> list : lists) {
            list.stream()
                .forEach(finalList::add);
        }

        // Return the final flattened list
        return finalList;
    }

    public static void main(String[] args)
    {

        // Get the map to be flattened.
        Map<Integer, List<Character> > map = new HashMap<>();
        map.put(1, Arrays.asList('G', 'e', 'e', 'k', 's'));
        map.put(2, Arrays.asList('F', 'o', 'r'));
        map.put(3, Arrays.asList('G', 'e', 'e', 'k', 's'));

        // Flatten the Stream
        List<Character> flatList = flattenStream(map.values());

        // Print the flattened list
        System.out.println(flatList);
    }
}
```

**Output:**

```java
[G, e, e, k, s, F, o, r, G, e, e, k, s]

```