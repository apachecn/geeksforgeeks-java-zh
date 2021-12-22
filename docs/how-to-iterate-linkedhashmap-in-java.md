# 如何在 Java 中迭代 LinkedHashMap？

> 原文:[https://www . geesforgeks . org/how-iterate-link edhashmap-in-Java/](https://www.geeksforgeeks.org/how-to-iterate-linkedhashmap-in-java/)

[LinkedHashMap](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 类扩展 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/#:~:text=HashMap%20is,type%20(e.g.%20an%20Integer).) 并按照条目插入的顺序维护地图中条目的链表。这允许在地图上进行插入顺序迭代。也就是说，当迭代 LinkedHashMap 时，元素将按照插入的顺序返回。

**迭代 LinkedHashMap 基本上有两种方式:**

1.  使用键集()和 get()方法
2.  使用 entrySet()和迭代器

**方法 1:** 使用[键集()](https://www.geeksforgeeks.org/hashmap-keyset-method-in-java/)和 [get()](https://www.geeksforgeeks.org/hashmap-get-method-in-java/) 方法迭代链接的哈希表

**语法:**

```
linked_hash_map.keySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个具有 LinkedHashMap 键的集合。

*   通过 keySet()方法，我们将获得一个具有映射键的集合。
*   然后在这个集合上运行一个循环之后，我们可以使用 get()方法获取每个键及其值。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to iterate through LinkedHashMap using 
// keySet() and get() Method

import java.util.LinkedHashMap;
import java.util.Set;

public class GFG {

    public static void main(String a[])
    {
        // making the object of LinkedHashMap
        LinkedHashMap<String, String> linkedHashMap
                 = new LinkedHashMap<String, String>();

        // adding the elements in linkedHashMap
        linkedHashMap.put("One", "First element");
        linkedHashMap.put("Two", "Second element");
        linkedHashMap.put("Three", "Third element");

        Set<String> keys = linkedHashMap.keySet();

        // printing the elements of LinkedHashMap
        for (String key : keys) {
            System.out.println(key + " -- "
                               + linkedHashMap.get(key));
        }

    }
}
```

**Output**

```
One -- First element
Two -- Second element
Three -- Third element

```

**方法 2:** 使用 [entrySet()](https://www.geeksforgeeks.org/hashmap-entryset-method-in-java/) 和[迭代器](https://www.geeksforgeeks.org/iterators-in-java/)迭代链接的散列表

**语法:**

```
Linkedhash_map.entrySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个与 LinkedHashMap 元素相同的集合。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to iterate over linkedHashMap using
// entrySet() and iterator

import java.util.Iterator;
import java.util.LinkedHashMap;
import java.util.Set;

public class GFG {

    public static void main(String[] args)
    {

        // Create a LinkedHashMap and populate it with
        // elements
        LinkedHashMap<String, String> linkedHashMap
            = new LinkedHashMap<String, String>();

        // adding the elements to the linkedHashMap
        linkedHashMap.put("One", "First element");
        linkedHashMap.put("Two", "Second element");
        linkedHashMap.put("Three", "Third element");

        // Get a set of all the entries (key - value pairs)
        // contained in the LinkesHashMap
        Set entrySet = linkedHashMap.entrySet();

        // Obtain an Iterator for the entries Set
        Iterator it = entrySet.iterator();

        // Iterate through LinkedHashMap entries
        System.out.println("LinkedHashMap entries : ");

        while (it.hasNext())
            // iterating over each element using it.next()
            // method
            System.out.println(it.next());
    }
}
```

**Output**

```
LinkedHashMap entries : 
One=First element
Two=Second element
Three=Third element

```