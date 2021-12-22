# Java 中列表、集合和映射的区别

> 原文:[https://www . geesforgeks . org/Java 中列表集和地图的区别/](https://www.geeksforgeeks.org/difference-between-list-set-and-map-in-java/)

[Java 中的列表界面](https://www.geeksforgeeks.org/list-interface-java-examples/)是 Java 集合界面的子界面。它包含基于索引的插入、更新、删除和搜索元素的方法。它也可以有重复的元素。我们还可以将空元素存储在列表中。列表保留插入顺序，它允许位置访问和元素插入。它可以在 java.util 包中找到。让我们考虑一下 a 的一个例子，更好地理解如何使用 java 中的 a list 接口添加元素。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate the
// addition of elements in a List

import java.util.*;
public class GFG {

    public static void main(String args[])
    {

        // Creating a List
        List<String> al = new ArrayList<>();

        // Adding elements in the List
        al.add("mango");
        al.add("orange");
        al.add("Grapes");

        // Iterating the List
        // element using for-each loop
        for (String fruit : al)
            System.out.println(fruit);
    }
}
```

**输出:**

```
mango
orange
Grapes
```

[](https://www.geeksforgeeks.org/set-in-java/)**集合遵循无序的方式，它在 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中找到，并在 java 中扩展了集合接口。集合中的重复项目将被忽略，并且不会在最终输出中打印。让我们考虑一个 a 更好理解的例子，在这里您将看到如何使用 java 中的 a set 接口来添加元素。让我们看看。**

****示例:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// A Java program to demonstrate a Set.
// Here, you will see how you can add
// Elements using Set.

import java.util.*;

public class SetExample {

    public static void main(String[] args)
    {
        // Set demonstration using HashSet
        Set<String> Set = new HashSet<String>();

        // Adding Elements 
        Set.add("one");
        Set.add("two");
        Set.add("three");
        Set.add("four");
        Set.add("five");

        // Set follows unordered way.
        System.out.println(Set);
    }
}
```

****输出:****

```
[four, one, two, three, five]
```

**[**Java Map 界面**](https://www.geeksforgeeks.org/map-interface-java-examples/) ，java.util.Map 表示一个键和值之间的映射。更具体地说，Java Map 可以存储成对的键和值。每个键都链接到一个特定的值。一旦存储在地图中，以后只需使用键就可以查找该值。让我们考虑一个 a 的例子，更好地理解如何使用 java 中的 Map 接口添加元素。让我们看看。**

****示例:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// A sample program to demonstrate Map.

// Here, you will see how you
// can add elements using Map
import java.util.*;

class MapExample {

    public static void main(String args[])
    {

        // Creating object for Map.
        Map<Integer, String> map
            = new HashMap<Integer, String>();

        // Adding Elements using Map.
        map.put(100, "Amit");
        map.put(101, "Vijay");
        map.put(102, "Rahul");

        // Elements can traverse in any order
        for (Map.Entry m : map.entrySet()) {
            System.out.println(m.getKey() + " "
                               + m.getValue());
        }
    }
}
```

****输出:****

```
100 Amit
101 Vijay
102 Rahul
```

****列表、** **集合****和 Java 中地图**的区别**

<figure class="table">

| 

[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)

 | 

[设置](https://www.geeksforgeeks.org/set-in-java/)

 | 

[地图](https://www.geeksforgeeks.org/map-interface-java-examples/)

 |
| --- | --- | --- |
| 列表界面允许重复元素 | 集合不允许重复元素。 | 地图不允许重复元素 |
| 列表保持插入顺序。 | Set 不维护任何插入顺序。 | 该映射也不维护任何插入顺序。 |
| 我们可以添加任意数量的空值。 | 但是在集合中几乎只有一个空值。 | 映射最多允许一个空键和任意数量的空值。

 |
| 列表实现类有[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)、[链表](https://www.geeksforgeeks.org/linked-list-in-java/)。 | 设置实现类有 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 、 [LinkedHashSet](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 、 [TreeSet](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 。 | 地图实现类有 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 、 [HashTable](https://www.geeksforgeeks.org/hashtable-in-java/) 、 [TreeMap](https://www.geeksforgeeks.org/treemap-in-java/) 、 [ConcurrentHashMap](https://www.geeksforgeeks.org/concurrenthashmap-in-java/) 、 [LinkedHashMap](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 。 |
| 该列表提供 get()方法来获取指定索引处的元素。 | Set 不提供 get 方法来获取指定索引处的元素 | 映射不提供 get 方法来获取指定索引处的元素 |
| 如果您需要经常使用索引来访问元素，那么我们可以使用列表 | 如果你想创建一个独特元素的集合，那么我们可以使用 set | 如果您想以键/值对的形式存储数据，那么我们可以使用映射。 |
| 使用列表过滤器遍历列表元素。 | 迭代器可以用来遍历集合元素 | 通过键集、值和入口集。 |

</figure>