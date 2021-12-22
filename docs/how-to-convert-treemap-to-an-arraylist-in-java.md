# 如何在 Java 中将 TreeMap 转换成 ArrayList？

> 原文:[https://www . geesforgeks . org/how-convert-tree map-to-a-ArrayList-in-Java/](https://www.geeksforgeeks.org/how-to-convert-treemap-to-an-arraylist-in-java/)

[**树形图**](https://www.geeksforgeeks.org/treemap-in-java/) 是 Java Collection 框架的一部分。Java TreeMap 包含基于键的值。它实现了导航映射接口并扩展了抽象映射类。它提供了一种以排序顺序存储键值对的有效方法。Java TreeMap 只包含唯一的元素。它不能有空键，但可以有多个空值。TreeMap 是不同步的，我们必须显式同步它，以便在多线程环境中使用它。树形图保持元素的**升序**。

**将树形图转换为** [**数组列表**](https://www.geeksforgeeks.org/arraylist-in-java/) **的方式:**

*   具有键和值的树形图可以转换成键和值的两个数组列表。
*   Als o 两个数组列表，一个带键另一个带值，可以转换成树形图。

**示例:**

```java
TreeMap : {1=Welcome, 2=To, 3= Geeks, 4=For, 5=Geeks}
keyList : [1, 2, 3, 4, 5]
valueList : [Welcome, To, Geeks, For, Geeks]
```

**进场:**

*   创建一个树形图对象，并插入一些键和值。
*   使用 TreeMap.keySet()方法从树映射中提取密钥，并将其放入为存储密钥而创建的数组列表对象中。
*   使用 TreeMap.values()方法从 TreeMap 中提取值，并将其放入为存储值而创建的另一个数组列表对象中。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate conversion of
// TreeMap to ArrayList

import java.util.*;
class GFG {
    // a class level treeMap object
    static TreeMap<Integer, String> treeMap
        = new TreeMap<Integer, String>();

    // Method to convert TreeMap to ArrayList
    static void convertMapToList()
    {
        // Extract the keys from the TreeMap
        // using TreeMap.keySet() and
        // assign them to keyList of type ArrayList
        ArrayList<Integer> keyList
            = new ArrayList<Integer>(treeMap.keySet());

        // Extract the values from the TreeMap
        // using TreeMap.values() and
        // assign them to valueList of type ArrayList
        ArrayList<String> valueList
            = new ArrayList<String>(treeMap.values());

        // printing the keyList
        System.out.println(
            "List of keys of the given Map : " + keyList);

        // printing the valueList
        System.out.println(
            "List of values of the given Map : "
            + valueList);
    }

    // Driver Method
    public static void main(String args[])
    {
        // inserting data into the TreeMap
        // using TreeMap.put() method
        treeMap.put(1, "Welcome");
        treeMap.put(2, "To");
        treeMap.put(3, "Geeks");
        treeMap.put(4, "For");
        treeMap.put(5, "Geeks");

        // printing the TreeMap
        System.out.println("The TreeMap is : " + treeMap);

        // calling convertMapToList() method
        convertMapToList();
    }
}
```

**Output**

```java
The TreeMap is : {1=Welcome, 2=To, 3=Geeks, 4=For, 5=Geeks}
List of keys of the given Map : [1, 2, 3, 4, 5]
List of values of the given Map : [Welcome, To, Geeks, For, Geeks]
```