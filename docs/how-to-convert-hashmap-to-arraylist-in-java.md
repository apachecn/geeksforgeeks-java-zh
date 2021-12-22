# 如何在 Java 中将 HashMap 转换为 ArrayList？

> 原文:[https://www . geesforgeks . org/how-convert-hashmap-to-ArrayList-in-Java/](https://www.geeksforgeeks.org/how-to-convert-hashmap-to-arraylist-in-java/)

[HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) 是从 Java 1.2 开始的 [Java 集合](https://www.geeksforgeeks.org/collections-in-java-2/)的一部分。它提供了 Java 的[地图界面](https://www.geeksforgeeks.org/map-interface-java-examples/)的基本实现。它以(键、值)对的形式存储数据。与 Hashmap 不同的是，[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)用于在 Java 中为我们提供动态数组。它是阵列的替代产品，在存储方面提供了更大的灵活性。在本文中，我们将看到如何将 Hashmap 转换为 ArrayList。
由于 hashmap 中的每个元素都包含一个键/值对，因此不可能将这个键/值对存储在单个 ArrayList 中。因此，为了将 hashmap 转换为 ArrayList，我们需要维护两个独立的 ArrayList，其中一个 ArrayList 用于存储 key，另一个用于存储对应于这些 key 的值。以下是用于将散列表转换为数组列表的各种方法。

### 方法 1:

转换的一种方法是使用数组列表的[构造函数](https://www.geeksforgeeks.org/java-gq/constructors-2-gq/)。为此，我们可以使用散列表中的[键集()方法](https://www.geeksforgeeks.org/hashmap-keyset-method-in-java/)。该方法返回包含散列表所有键的[集](https://www.geeksforgeeks.org/set-in-java/)。这个集合可以在初始化时传递到数组列表中，以便获得包含所有键的数组列表。在获取键之后，我们可以使用 hashmap 中存在的 values()方法来获取 hashmap 中存在的所有值的集合。我们可以使用这个集合来初始化另一个数组，该数组包含 hashmap 中键的所有值。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert a HashMap
// to an ArrayList

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create an empty hash map
        HashMap<String, Integer> map
            = new HashMap<>();

        // Add elements to the map
        map.put("vishal", 10);
        map.put("sachin", 30);
        map.put("vaibhav", 20);

        // Finding the Set of keys from
        // the HashMap
        Set<String> keySet = map.keySet();

        // Creating an ArrayList of keys
        // by passing the keySet
        ArrayList<String> listOfKeys
            = new ArrayList<String>(keySet);

        // Getting Collection of values from HashMap
        Collection<Integer> values = map.values();

        // Creating an ArrayList of values
        ArrayList<Integer> listOfValues
            = new ArrayList<>(values);

        System.out.println("The Keys of the Map are "
                           + listOfKeys);

        System.out.println("The Values of the Map are "
                           + listOfValues);
    }
}
```

**输出:**

```
The Keys of the Map are [vaibhav, vishal, sachin]
The Values of the Map are [20, 10, 30]
```

**注意:**在上面的例子中，可以清楚地观察到，键和值之间的相关性由数组列表的索引保留。这意味着可以在值列表中的同一索引处找到特定键的值。

### 方法 2:

将哈希表转换为数组列表的另一种方法是使用[流应用编程接口](https://www.geeksforgeeks.org/stream-in-java/)将映射键和值转换为相应的列表。
T3】

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert a HashMap
// to an ArrayList

import java.util.*;
import java.util.stream.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create an empty hash map
        HashMap<String, Integer> map
            = new HashMap<>();

        // Add elements to the map
        map.put("vishal", 10);
        map.put("sachin", 30);
        map.put("vaibhav", 20);

        // Java 8 code to convert map keys to list
        // Here, the collect() method collects the
        // stream of keys in a ArrayList.
        ArrayList<String> listOfKeys
            = map.keySet().stream().collect(
                Collectors.toCollection(ArrayList::new));

        // Java 8 code to convert map values to list
        ArrayList<Integer> listOfValues
            = map.values().stream().collect(
                Collectors.toCollection(ArrayList::new));

        System.out.println("The Keys of the Map are "
                           + listOfKeys);

        System.out.println("The Values of the Map are "
                           + listOfValues);
    }
}
```

**输出:**

```
The Keys of the Map are [vaibhav, vishal, sachin]
The Values of the Map are [20, 10, 30]
```

**注意:**将 collectors . to collection(ArrayList::new)传递给 collect()方法，作为新的 ArrayList 进行收集。我们也可以使用 [toList()](https://www.geeksforgeeks.org/collectors-tolist-method-in-java-with-examples/) 来代替这个函数，将它转换成 List，然后再转换成任何其他 List 实现。&

### 方法 3:

在上述两种方法中，HashMap 被转换为 ArrayList，而不保留直接键/值关系。键和值存储在两个不同的数组列表中。但是，我们可以使用 [entrySet()](https://www.geeksforgeeks.org/hashmap-entryset-method-in-java/) 方法保留数组列表中的键/值对。此方法用于创建哈希映射中包含的相同元素的集合。它基本上返回哈希映射的集合视图，或者我们可以创建一个新的集合并将映射元素存储到其中。我们可以使用构造函数将这个集合传递到数组列表中，以便形成一个以[条目对象](https://www.geeksforgeeks.org/map-entry-interface-java-example/)为键/值对的数组列表。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert a HashMap
// to an ArrayList

import java.util.*;
import java.util.stream.*;
import java.util.Map.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create an empty hash map
        HashMap<String, Integer> map
            = new HashMap<>();

        // Add elements to the map
        map.put("vishal", 10);
        map.put("sachin", 30);
        map.put("vaibhav", 20);

        // Set of the entries from the
        // HashMap
        Set<Map.Entry<String, Integer> > entrySet
            = map.entrySet();

        // Creating an ArrayList of Entry objects
        ArrayList<Map.Entry<String, Integer> > listOfEntry
            = new ArrayList<Entry<String, Integer> >(entrySet);

        System.out.println(listOfEntry);
    }
}
```

**输出:**

```
[vaibhav=20, vishal=10, sachin=30]
```