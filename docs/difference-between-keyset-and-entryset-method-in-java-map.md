# Java Map 中 keySet()和 entrySet()方法的区别

> 原文:[https://www . geesforgeks . org/key set-and-entryset-method-in-Java-map/](https://www.geeksforgeeks.org/difference-between-keyset-and-entryset-method-in-java-map/)

[映射接口](https://www.geeksforgeeks.org/map-interface-java-examples/)存在于 Java.util 包中，主要提供了 KeySet()、entrySet()和值()三种方法。这些方法分别用于检索地图的键、地图的键值对以及地图的值。因为这些方法是映射接口的一部分，所以我们可以将这些方法用于所有实现映射接口的类，如 TreeMap、HashMap 和 LinkedHashMap。

[**键集()方法:**](https://www.geeksforgeeks.org/hashmap-keyset-method-in-java/)

java 中的 java.util.HashMap.keySet()方法用于创建一组包含在哈希映射中的关键元素。它基本上返回一个键的集合视图，或者我们可以创建一个新的集合并将键元素存储在其中。

**语法:**

```
hash_map.keySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个具有哈希映射键的集合。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program demonstrating use of keySet()

import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.stream.Stream;

class GFG {
    public static void main(String[] args)
    {
        // making map of Integer keys and String values
        Map<Integer, String> map = new HashMap<>();

        // adding the key-value pairs to map
        map.put(1, "Geeks");
        map.put(2, "For");
        map.put(3, "Geeks");

        // below are the different and simple ways out of
        // many  to iterate over the keySet()

        // iterating the keySet() using iterator
        Iterator<Integer> itr = map.keySet().iterator();

        while (itr.hasNext())
        {
            System.out.print(itr.next() + " ");
        }
        System.out.println();

        // iterating the keySet() using for loop
        for (Integer key : map.keySet()) {
            System.out.print(key + " ");
        }

        System.out.println();

        // iterating over the keySet() by converting the map
        // to the string
        System.out.println(map.keySet().toString());
    }
}
```

**Output**

```
1 2 3 
1 2 3 
[1, 2, 3]

```

[**entrySet()方法**](https://www.geeksforgeeks.org/hashmap-entryset-method-in-java/)T4:

java 中的 java.util.HashMap.entrySet()方法用于创建一组包含在哈希映射中的相同元素。它基本上返回哈希映射的集合视图，或者我们可以创建一个新的集合并将映射元素存储到其中。

**语法:**

```
hash_map.entrySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个与哈希映射具有相同元素的集合。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program demonstrating use of  entrySet()

import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.stream.Stream;

class GFG {
    public static void main(String[] args)
    {
        // making map of Integer keys and String values
        Map<Integer, String> map = new HashMap<>();

        // adding the key-value pairs to map
        map.put(1, "Geeks");
        map.put(2, "For");
        map.put(3, "Geeks");

        // below are the different and simple ways out of
        // many  to iterate over the entrySet()

        // iterating the key value pair using for each loop
        for (Map.Entry<Integer, String> entry :map.entrySet()) 
        {
            Integer key = (Integer)entry.getKey();
            String value = entry.getValue();

            System.out.println(key + "=" + value);
        }

        // iterating the key-value pairs using iterator
        Iterator<Map.Entry<Integer, String> > itr = map.entrySet().iterator();

        while (itr.hasNext()) {
            System.out.println(itr.next());
        }

        // iterating the key-value pairs using Stream.of()
        // method
        Stream.of(map.entrySet().toArray())
            .forEach(System.out::println);
    }
}
```

**Output**

```
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

<figure class="table">

| 密钥集() | entrySet() |
| --- | --- |
| 该方法返回地图中所有关键点的集合视图，即返回一组关键点。 | 这个方法返回映射中所有映射的集合视图，即它返回一组键值对。 |
| 如果地图发生任何变化，那么它们也可以在集合中观察到，因为集合是由地图备份的。 | 同样对于 entrySet()方法，如果地图发生任何变化，那么它们也可以在集合中观察到，因为集合是由地图备份的。 |
| 如果使用 keySet()迭代所有映射对，那么与 entrySet()相比，keySet()的性能较差，因为对于每个键，我们必须使用 get()函数来访问其对应的值。 | 当使用 entrySet()遍历映射的所有对时，entrySet()的性能比 keySet()好得多。 |

</figure>