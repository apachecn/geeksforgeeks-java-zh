# 【ConcurrentHashMap 和 SynchronizedHashMap 的区别

> 原文:[https://www . geesforgeks . org/difference-concurrenthashmap-and-synchronized hashmap/](https://www.geeksforgeeks.org/difference-between-concurrenthashmap-and-synchronizedhashmap/)

ConcurrentHashMap 和 SynchronizedHashMap 都是线程安全的 Collection 类，可以在多线程和并发 java 应用程序中使用。但是它们之间几乎没有区别。在本文中，我们试图涵盖它们之间的所有这些差异。

**1。**[**ConcurrentHashMap**](https://www.geeksforgeeks.org/concurrenthashmap-in-java/)**:**ConcurrentHashMap 是实现 ConcurrentMap 接口的类。它使用[哈希表](https://www.geeksforgeeks.org/hashtable-in-java/)，带下划线的数据结构。正如我们所知，在我们的应用程序中处理线程时 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) 不是一个好的选择，因为性能问题。为了解决这个问题，我们在应用程序中使用了 ConcurrentHashMap。ConcurrentHashMap 是线程安全的，因此多个线程可以对单个对象进行操作，没有任何问题。在 ConcurrentHashMap 中，对象根据并发级别被分成多个段。默认情况下，它允许 16 个线程从[映射](https://www.geeksforgeeks.org/map-interface-java-examples/)读写，无需任何同步。在 ConcurrentHashMap 中，任何数量的线程都可以执行检索操作，但是为了更新对象，线程必须锁定线程想要操作的特定段。这种锁定机构称为**分段锁定或铲斗锁定**。因此，有时 16 个更新操作可以由线程执行。

**ConcurrentHashMap 演示:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to demonstrate the
// working of ConcurrentHashMap

import java.util.*;
import java.util.concurrent.*;

public class TraversingConcurrentHashMap {

    public static void main(String[] args)
    {

        // create an instance of ConcurrentHashMap
        ConcurrentHashMap<Integer, String> chmap
            = new ConcurrentHashMap<Integer, String>();

        // Add elements using put()
        chmap.put(10, "Geeks");
        chmap.put(20, "for");
        chmap.put(30, "Geeks");
        chmap.put(40, "Welcome");
        chmap.put(50, "you");

        // Create an Iterator over the
        // ConcurrentHashMap
        Iterator<ConcurrentHashMap.Entry<Integer, String> >
            itr = chmap.entrySet().iterator();

        // The hasNext() method is used to check if there is
        // a next element and the next() method is used to
        // retrieve the next element
        while (itr.hasNext()) {
            ConcurrentHashMap.Entry<Integer, String> entry
                = itr.next();
            System.out.println("Key = " + entry.getKey()
                               + ", Value = "
                               + entry.getValue());
        }
    }
}
```

**Output**

```java
Key = 50, Value = you
Key = 20, Value = for
Key = 40, Value = Welcome
Key = 10, Value = Geeks
Key = 30, Value = Geeks
```

**2。同步 HashMap:** Java HashMap 是一个非同步的集合类。如果我们需要对它执行线程安全操作，那么我们必须显式地同步它。使用 [java.util.Collections](https://www.geeksforgeeks.org/collections-class-in-java/) 类的 [synchronizedMap()](https://www.geeksforgeeks.org/collections-synchronizedmap-method-in-java-with-examples/) 方法进行同步。它返回由指定映射支持的同步(线程安全)映射。

**同步 HashMap 演示:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the
// working of Synchronized HashMap

import java.util.Collections;
import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.Set;

public class SynchronizedHashMap {
    public static void main(String args[])
    {

        // Creating a HashMap
        HashMap<Integer, String> hmap
            = new HashMap<Integer, String>();

        // Adding the elements using put method
        hmap.put(10, "Geeks");
        hmap.put(20, "for");
        hmap.put(30, "Geeks");
        hmap.put(25, "Welcome");
        hmap.put(40, "you");

        // Creating a synchronized map
        Map map = Collections.synchronizedMap(hmap);
        Set set = map.entrySet();

        // Synchronize on HashMap, not on set
        synchronized (map)
        {
            Iterator i = set.iterator();
            // Printing the elements
            while (i.hasNext()) {
                Map.Entry me = (Map.Entry)i.next();
                System.out.print(me.getKey() + ": ");
                System.out.println(me.getValue());
            }
        }
    }
}
```

**Output**

```java
20: for
40: you
25: Welcome
10: Geeks
30: Geeks
```

【ConcurrentHashMap 和 Synchronized HashMap 的区别:

<figure class="table">

| ConcurrentHashMap | 同步哈希表 |
| ConcurrentHashMap 是一个实现 ConcurrentMap 和 [serializable](https://www.geeksforgeeks.org/serializable-interface-in-java/) 接口的类。 | 我们可以使用 java.util.Collections 类的 **synchronizedMap()** 方法来同步 HashMap。 |
| 它锁定了地图的某个部分。 | 它锁定了整个地图。 |
| ConcurrentHashMap 允许执行并发读写操作。因此，性能相对优于同步映射。 | 在同步哈希表中，多个线程不能同时访问映射。因此，性能相对低于 ConcurrentHashMap。 |
| ConcuurentHashMap 不允许将 null 作为键或值插入。 | 同步哈希表允许插入空值作为关键字。 |
| ConccurentHashMap 不抛出 ConcurrentModificationException。 | 同步哈希表抛出**并发修改异常**。 |

</figure>