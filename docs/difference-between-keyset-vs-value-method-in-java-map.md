# Java Map 中 keySet()与 value()方法的区别

> 原文:[https://www . geesforgeks . org/key set-vs-value-method-in-Java-map/](https://www.geeksforgeeks.org/difference-between-keyset-vs-value-method-in-java-map/)

[映射](https://www.geeksforgeeks.org/map-interface-java-examples/)接口在 Java.util 包中有，主要提供了 KeySet()，entrySet()和值()三种方法。这些方法分别用于检索地图的键、地图的键值对以及地图的值。由于这些方法是地图接口的一部分，所以我们可以将这些方法用于所有实现地图接口的类，如[树地图](https://www.geeksforgeeks.org/treemap-in-java/)、[哈希表](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)和[链接哈希表](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/)。

为了找出差异，让我们首先从概念上逐个分析它们，然后在实现中找出它们之间的主要差异。

**方法 1:** [*键集()*方法](https://www.geeksforgeeks.org/map-keyset-method-in-java-with-examples/)

此方法用于返回此地图中包含的键的集合视图。集合由地图支持，因此对地图的更改会反映在集合中，反之亦然。

**语法:**

```java
Set keySet()
```

**参数:**这个方法没有参数。

**返回:**该方法返回一个包含指定地图关键点的集合。

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program demonstrating use of keySet() method

// Importing HashMap, Iterator, MAp and Stream classes
// from java.util package
import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.stream.Stream;

// Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating object of Map Class
        // Declaring object of Interfere and string type
        Map<Integer, String> map = new HashMap<>();

        // Adding the elements to the objects
        // Elements here are key-value pairs in the map

        // Custom input entries
        map.put(1, "Geeks");
        map.put(2, "For");
        map.put(3, "Geeks");

        // Now, different ways of iteration are illustrated
        // to showcase keySet() method

        // Way 1
        // Iterating the keySet() using iterator

        // Creating an object of Integer type
        Iterator<Integer> itr = map.keySet().iterator();

        // Condition check where hasNext() method holds true
        // till there is single element remaining in th List
        while (itr.hasNext()) {

            // Print all the elements(key-value pairs)
            System.out.print(itr.next() + " ");
        }

        // New line
        System.out.println();

        // Way 2
        // Iterating the keySet()
        // using for loop
        for (Integer key : map.keySet()) {

            // Print all the key-value pairs
            System.out.print(key + " ");
        }

        // New line
        System.out.println();

        // Way 3
        // Iterating over the keySet() by
        // converting the map to the string
        // using the toString() method
        System.out.println(map.keySet().toString());
    }
}
```

**Output**

```java
1 2 3 
1 2 3 
[1, 2, 3]
```

**方法二:** [*价值观()方法*](https://www.geeksforgeeks.org/hashmap-values-method-in-java/)

java 中 HashMap 类的*Java . util . HashMap . values()*方法用于从映射的值中创建一个集合。它基本上返回哈希表中值的集合视图。

**语法:**

```java
Hash_Map.values()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法用于返回包含地图所有值的集合视图。

**实现:**下面是使用*值()*方法的 Java 程序

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program demonstrating use of values() method

// Importing several classes from
// java.util package
import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.stream.Stream;

// Class
// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Making map of Integer keys and String values
        Map<Integer, String> map = new HashMap<>();

        // Adding the elements to the above object
        // Declaring object of Integer and String type

        // Elements here are key-value pairs
        // Custom input entries
        map.put(1, "Geeks");
        map.put(2, "For");
        map.put(3, "Geeks");

        // values() method implemented by
        // demonstrating different ways of traversal

        // Way 1
        // Iterating the values() method
        // using iterator
        Iterator itr = map.values().iterator();

        // Condition check using hasNet() method which
        // holds true till there is single element remaining
        while (itr.hasNext()) {
            System.out.print(itr.next() + " ");
        }
        System.out.println();

        // Way 2
        // Iterating the values() method
        // using for each loop
        for (String key : map.values()) {
            System.out.print(key + " ");
        }
        System.out.println();

        // Way 3
        // iterating over the values() method
        // by converting the map to the string
        // using the toString() method
        System.out.println(map.values().toString());
    }
}
```

**Output**

```java
Geeks For Geeks 
Geeks For Geeks 
[Geeks, For, Geeks]
```

现在终于到结论了，让我们看看键集()方法和值()方法之间的区别如下:

<figure class="table">

| keySet()方法 | values()方法 |
| --- | --- |
| 该方法返回地图中所有关键点的集合视图，即返回一组关键点。 | 此方法返回地图中包含的所有值的集合视图。 |
| 如果地图发生任何变化，那么它们也可以在集合中观察到，因为  集合是由地图备份的。 | 如果地图发生任何变化，也可以在集合中观察到这些变化，因为集合是由地图备份的。 |
| 只有当我们需要处理地图中存在的所有关键点时，才使用这种方法。 | 当我们只需要处理地图中存在的所有值时，就可以使用这种方法。 |

</figure>