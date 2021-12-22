# Java 地图到列表的转换

> 原文:[https://www . geesforgeks . org/转换-java-maps-to-list/](https://www.geeksforgeeks.org/conversion-of-java-maps-to-list/)

一个[映射](https://www.geeksforgeeks.org/map-interface-java-examples/)是一个将键映射到值的对象，或者是属性值对的集合。列表是对象的有序集合，列表可以包含重复的值。映射有两个值(键和值)，而列表只有一个值(元素)。因此，我们可以从一个地图中生成两个列表，如下所示:

*   List of values and
*   Key list.

让我们假设“**map”**是 Map 的实例，此后像往常一样我们都知道它包含集合和值对。因此它们的定义如下:

*   **map.values ()** will return a set of map values.
*   **map.keyset ()** will return a set of key points of the map.

**方法:**

1.  Constructs the function parameter of the array list.
2.  Is passed to the array list constructor parameter.
3.  (only applicable to JDK 8 and later versions)

让我们逐一讨论

**方法 1:** 在数组列表构造函数参数中传递键集

**程序:**我们可以绕过 map.keySet()方法生成的一组映射键，将映射键转换为键列表，转换为 ArrayList 构造函数参数，如下图所示

```java
map.values(); // Now here e will pass sets of keys of our map, so it becomes
map.values(map.keySet());  // Now we just need to store it into List, so creating object 
List ListofKeys = new ArrayList(map.keySet()); // Now we are done with conversion. 
```

**语法:**此后如下:

```java
List ListofKeys = new ArrayList(map.keySet());
```

**方法 2:**List List of keys = new ArrayList(map . keyset())；

我们可以通过将 [*map.values()方法*](https://www.geeksforgeeks.org/hashmap-values-method-in-java/) 生成的映射值集合传递给数组列表构造函数参数，将映射键转换为值列表。

**语法:**此后如下:

```java
List Listofvalues = new ArrayList(map.values());
```

**例**

## 爪哇

```java
// Java Program to Convert Map to List

// Importing required classes
import java.util.*;

class GFG {

    // Method 1
    public static void main(String[] args)
    {

        // Creating HashMap
        HashMap<String, Integer> hs = new HashMap<>();

        // Adding elements to hashMap
        hs.put("Geeks", 1);
        hs.put("for", 2);
        hs.put("Geeks", 3);
        hs.put("Computer", 4);
        hs.put("Science", 5);
        hs.put("Portal", 6);

        // Calling method
        MapValuesToList obj = new MapValuesToList(hs);

        // Storing into List
        List<Integer> mapvaltolist = obj.mapvaltolist(hs);

        // Printing via for loops
        for (Integer integerList : mapvaltolist) {

            // Printing our ArrayList
            System.out.println(integerList);
        }
    }

    // Method 2
    // To convert Map to List
    public List<String>
    mapvaltolist(Map<String, Integer> map)
    {

        // Using Collection
        Collection<Integer> val = map.values();

        // Creating an ArrayList
        ArrayList<Integer> al = new ArrayList<>(values);

        return al;
    }
}
```