# Java 地图中值()与 entrySet()方法的差异

> 原文:[https://www . geesforgeks . org/value-vs-entryset-method-in-Java-map/](https://www.geeksforgeeks.org/difference-between-value-vs-entryset-method-in-java-map/)

[映射](https://www.geeksforgeeks.org/map-interface-java-examples/)接口在 Java.util 包中有，主要提供了三种方法 KeySet()，entrySet()和值()。这些方法分别用于检索地图的键、地图的键值对以及地图的值。由于这些方法是地图接口的一部分，所以我们可以将这些方法用于所有实现地图接口的类，如[树地图](https://www.geeksforgeeks.org/treemap-in-java/)、[哈希表](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)和[链接哈希表](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/)。

**法 1:** [*值()*法](https://www.geeksforgeeks.org/hashmap-values-method-in-java/)

java 中 HashMap 类的 java.util.HashMap.values()方法用于从映射的值中创建一个集合。它基本上返回哈希表中值的集合视图。

**语法:**

```java
Hash_Map.values()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法用于返回包含地图所有值的集合视图。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program demonstrating use of values() method

// Importing all input output classes
import java.io.*;
// Importing HashMap, Iterator, Map and Stream classes
// from the java.util package
import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.stream.Stream;

// Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a Map object
        // Declaring object of String and integer type
        Map<Integer, String> map = new HashMap<>();

        // Now, adding the elements to the object created
        // Elements here are key- \value pairs

        // Custom input objects
        map.put(1, "Geeks");
        map.put(2, "For");
        map.put(3, "Geeks");

        // Showcasing different ways to illustrate
        // values() method

        // Way 1 - Using iterator
        // Iterating over the object elements of the
        // showcasing the values() method using iterator

        // Creating an object of Integer type
        Iterator<String> itr = map.values().iterator();

        // Condition check which holds true till
        // there is single elementusing hasNext() method
        while (itr.hasNext()) {

            // Travering across the elements elements
            // using next() method

            // Printing the elements in the object
            System.out.print(itr.next() + " ");
        }

        // New line
        System.out.println();

        // Way 2 - Using loops
        // Iterating over the elements using for-each loop
        // to showacase value() method
        for (String key : map.values()) {

            // Printing all the element in object
            // key-value pairs
            System.out.println(key);
        }

        // New line
        System.out.println();

        // Iterating over the values() method by
        // converting the Map to the string
        System.out.println(map.values().toString());
    }
}
```

**Output**

```java
Geeks For Geeks 
Geeks
For
Geeks

[Geeks, For, Geeks]
```

**方法二:** [*entrySet()*](https://www.geeksforgeeks.org/hashmap-entryset-method-in-java/) 方法

java 中的*Java . util . hashmap . entryset()*方法用于创建一组包含在哈希映射中的相同元素。它基本上返回哈希映射的集合视图，或者我们可以创建一个新的集合并将映射元素存储到其中。

**语法:**

```java
hash_map.entrySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个与哈希映射具有相同元素的集合。

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program demonstrating use of entrySet() method

//  Importing Map,Stream, hashMap and Iterator classes
// from the java.util package
import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.stream.Stream;

// Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of Map class
        // Declaring object of Integer and String type
        Map<Integer, String> map = new HashMap<>();

        // Now, adding the elements to the object
        // Here elements are key-value pairs to map

        // Custom input elements
        map.put(1, "Geeks");
        map.put(2, "For");
        map.put(3, "Geeks");

        // Now, proposing different cases in which we will
        // be iterating over the elements using entrySet()

        // Case 1
        // Iterating the key value pairs
        // using for each loop
        for (Map.Entry<Integer, String> entry :
             map.entrySet()) {

            // Corresponding key
            Integer key = (Integer)entry.getKey();

            // Corresponding pair
            String value = entry.getValue();

            // Printing all the corresponding key-value
            // pairs
            System.out.println(key + "=" + value);
        }

        // Case 2
        // Iterating the key-value pairs
        // using iterator
        Iterator<Map.Entry<Integer, String> > itr
            = map.entrySet().iterator();

        // Condition check using hasNext() method holding
        // true till there is single entry remaining
        while (itr.hasNext()) {

            // Go on printing key-value pairs
            System.out.println(itr.next());
        }

        // Case 3
        // Iterating and printing the key-value pairs
        // using Stream.of() method

        // Printing alongside by using scope resolution
        // operator
        Stream.of(map.entrySet().toArray())
            .forEach(System.out::println);
    }
}
```

**Output**

```java
1=Geeks
2=For
3=Geeks
1=Geeks
2=For
3=Geeks
1=Geeks
2=For
3=Geeks
```

现在让我们看看 values()方法和 entrySet()方法之间的区别

<figure class="table">

| 值()方法 | entrySet()方法 |
| --- | --- |
| 这个 *m* 方法返回地图中包含的所有值的集合视图。 | 这个方法返回映射中所有映射的集合视图，即它返回一组键值对。 |
| 如果地图发生了任何更改，那么也可以在集合中观察到这些更改，因为方法集合由地图备份。 | 如果地图发生任何变化，那么也可以在集合中观察到这些变化，因为集合是由地图备份的。 |
| 当我们只需要处理地图中存在的值时，使用这种方法。 | 当我们需要处理地图中存在的键和值时，使用这种方法。 |

</figure>