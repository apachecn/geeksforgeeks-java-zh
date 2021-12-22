# 找到一个元素在 Java 树形图中的位置

> 原文:[https://www . geesforgeks . org/find-a-Java-tree map 中元素的位置/](https://www.geeksforgeeks.org/find-the-position-of-an-element-in-a-java-treemap/)

给定一个元素 N 和一个树形图，任务是在 Java 中找到这个元素在给定树形图中的位置。

**示例:**

> **输入:**tree map = { 10 =极客，15=4，20 =极客，25 =欢迎，30 =你}，N = 20
> **输出:** 2
> 
> **输入:**tree map = { 10 =极客，15=4，20 =极客，25 =欢迎，30 =你}，N = 5
> **输出:** -1

**进场:**

*   没有直接的方法来找出键在树形图中的位置。
*   但是，我们可以使用 [TreeMap 头图()方法](https://www.geeksforgeeks.org/treemap-headmap-method-in-java/)。
*   方法返回树图中键严格小于 key_point 键的部分。
*   因此，如果键存在于树图中，那么它的头映射的大小()等于键在树图中的位置。

下面是上述方法的实现:

```
// Java code to find the position
// of an element in a Java TreeMap

import java.util.*;

public class Tree_Map_Demo {

    // Function to return the position of
    // the specified element in the given TreeMap
    public static <K, V> int findPosition(K N, TreeMap<K, V> tree_map)
    {
        int pos = -1;

        // Check if the given key
        // is present or not
        if (tree_map.containsKey(N)) {

            // If present, find the position
            // using the size of headMap()

            pos = tree_map.headMap(N).size();
        }

        return pos;
    }

    // Function to print the result
    public static <K, V> void printResult(K N, TreeMap<K, V> tree_map)
    {

        // Get the position
        int pos = findPosition(N, tree_map);

        // Print the result
        if (pos >= 0) {

            System.out.println(N + " found at "
                               + "position = " + pos);
        }
        else {

            System.out.println(N + " not found. "
                               + "Hence position = "
                               + pos);
        }
    }

    // Driver code
    public static void main(String[] args)
    {

        // Creating an empty TreeMap
        TreeMap<Integer, String> tree_map
            = new TreeMap<Integer, String>();

        // Mapping string values to int keys
        tree_map.put(10, "Geeks");
        tree_map.put(15, "4");
        tree_map.put(20, "Geeks");
        tree_map.put(25, "Welcomes");
        tree_map.put(30, "You");

        // Displaying the TreeMap
        System.out.println("TreeMap: " + tree_map);

        // Element of which position is to be found
        int N1 = 20, N2 = 5;

        // Get the position
        printResult(N1, tree_map);
        printResult(N2, tree_map);
    }
}
```

**Output:**

```
TreeMap: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
20 found at position = 2
5 not found. Hence position = -1

```