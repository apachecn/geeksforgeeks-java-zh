# 如何在 Java 中同步 HashMap？

> 原文:[https://www . geesforgeks . org/how-synchronize-hashmap-in-Java/](https://www.geeksforgeeks.org/how-to-synchronize-hashmap-in-java/)

[**HashMap**](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) 是 Collection 的 java 框架的一部分。它以键值对的形式存储数据。HashMap 的这些值可以通过使用它们各自的键来访问。键值对可以使用它们的索引(整数类型)来访问。

HashMap 类似于 java 中的 [HashTable](https://www.geeksforgeeks.org/hashtable-in-java/) 。哈希表和哈希表的主要区别在于哈希表是同步的，而哈希表不是同步的。此外，一个哈希映射可以有一个空键和任意数量的空值。哈希映射中不保留插入顺序。

**同步**是指控制多个线程对任意共享资源的访问。一次只能有一个线程访问同步的资源。

可以使用[**collections . synchronized map()**](https://www.geeksforgeeks.org/collections-synchronizedmap-method-in-java-with-examples/)方法同步 HashMap。

Java . util . collections类的**synchronized map()**方法用于返回由指定映射支持的同步(线程安全)映射。为了保证串行访问，通过返回的映射完成对后备映射的所有访问是至关重要的。

**语法:**

> *公共静态< K，V >地图< K，V >同步地图(地图< K，V > m)*

**参数:**该方法将**地图**作为参数“包裹”在同步地图中。

**返回值:**该方法返回指定地图的**同步视图**。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// synchronization of HashMap

import java.util.*;

public class GFG {
    public static void main(String[] argv) throws Exception
    {

        try {
            // create a HashMap object
            Map<String, String> hMap
                = new HashMap<String, String>();

            // add elements into the Map
            hMap.put("1", "Welcome");
            hMap.put("2", "To");
            hMap.put("3", "Geeks");
            hMap.put("4", "For");
            hMap.put("5", "Geeks");

            System.out.println("Map : " + hMap);

            // Synchronizing the map
            Map<String, String> sMap
                = Collections.synchronizedMap(hMap);

            // printing the Collection
            System.out.println("Synchronized map is : "
                               + sMap);
        }

        catch (IllegalArgumentException e) 
        {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output**

```
Map : {1=Welcome, 2=To, 3=Geeks, 4=For, 5=Geeks}
Synchronized map is : {1=Welcome, 2=To, 3=Geeks, 4=For, 5=Geeks}
```