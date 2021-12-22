# 通过键和值对哈希表进行排序的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-sort-a-hashmap-by-key-and-values/](https://www.geeksforgeeks.org/java-program-to-sort-a-hashmap-by-keys-and-values/)

[HashMap < K，V >](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) 是一个 Java 集合，是 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)的一部分。提供了 Java 的[地图](https://www.geeksforgeeks.org/map-interface-java-examples/)界面的基本实现。它以键和值对的形式存储数据，其中键必须是唯一的，但对值没有限制。如果我们尝试插入重复的键，它将替换相应键的元素。

**哈希表按值排序**

其思想是将条目集存储在列表中，然后在[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)的帮助下，使用 [Collections.sort()](https://www.geeksforgeeks.org/collections-sort-java-examples/) 方法基于值对列表进行排序。然后从列表中获取每个键的值，然后显示结果。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to sort Hashmap based on values

import java.lang.*;
import java.util.*;

public class GFG {

    // function to sort hashmap based on values
    public static HashMap<String, Integer>
    sortByValue(HashMap<String, Integer> hm)
    {
        // Creating a list from elements of HashMap
        List<Map.Entry<String, Integer> > list
            = new LinkedList<Map.Entry<String, Integer> >(
                hm.entrySet());

        // Sorting the list using Collections.sort() method
        // using Comparator
        Collections.sort(
            list,
            new Comparator<Map.Entry<String, Integer> >() {
                public int compare(
                    Map.Entry<String, Integer> object1,
                    Map.Entry<String, Integer> object2)
                {
                    return (object1.getValue())
                        .compareTo(object2.getValue());
                }
            });

        // putting the  data from sorted list back to hashmap
        HashMap<String, Integer> result
            = new LinkedHashMap<String, Integer>();
        for (Map.Entry<String, Integer> me : list) {
            result.put(me.getKey(), me.getValue());
        }

        // returning the sorted HashMap
        return result;
    }

    // Driver Code
    public static void main(String[] args)
    {
        // creating object of HashMap class
        HashMap<String, Integer> hashmap
            = new HashMap<String, Integer>();

        // inserting key-value pair into hashmap
        hashmap.put("five", 5);
        hashmap.put("seven", 7);
        hashmap.put("three", 3);
        hashmap.put("nine", 9);
        hashmap.put("zero", 0);
        hashmap.put("eight", 8);

        // sorting the HashMap based on values
        Map<String, Integer> map = sortByValue(hashmap);

        // print the sorted hashmap(based on values)
        for (Map.Entry<String, Integer> entry :
             map.entrySet()) {
            System.out.println("Key : " + entry.getKey()
                               + ", Value : "
                               + entry.getValue());
        }
    }
}
```

**Output**

```java
Key : zero, Value : 0
Key : three, Value : 3
Key : five, Value : 5
Key : seven, Value : 7
Key : eight, Value : 8
Key : nine, Value : 9
```

**哈希映射按键排序**

其思想是将 HashMap 的所有数据放入[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)中。然后将 HashMap 的所有键提取到一个数组列表中。接下来，使用 **Collections.sort()** 方法对提取的键进行排序，然后使用 [get()](https://www.geeksforgeeks.org/hashmap-get-method-in-java/) 方法对每个键提取其值。最后，地图根据其关键字进行排序。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Code to sort Map by key value
import java.util.*;
class GFG {

    // This map stores unsorted values
    static HashMap<Integer, String> m = new HashMap<>();

    // Function to sort map by Key
    public static void sortMapByKey()
    {
        ArrayList<Integer> sortKeys
            = new ArrayList<Integer>(m.keySet());

        Collections.sort(sortKeys);

        // Getting value for each key and displaying
        // results.
        for (Integer x : sortKeys)
            System.out.println("Key = " + x
                               + ", Value = " + m.get(x));
    }

    // Driver Code
    public static void main(String args[])
    {
        // putting values in the Map
        m.put(7, "seven");
        m.put(5, "five");
        m.put(1, "one");
        m.put(3, "three");
        m.put(9, "nine");

        // Calling the function to sortMapByKey to
        // perform sorting based on keys
        sortMapByKey();
    }
}
```

**Output**

```java
Key = 1, Value = one
Key = 3, Value = three
Key = 5, Value = five
Key = 7, Value = seven
Key = 9, Value = nine
```