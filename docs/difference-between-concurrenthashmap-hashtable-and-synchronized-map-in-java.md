# Java 中并发哈希表、哈希表和同步映射的区别

> 原文:[https://www . geesforgeks . org/difference-concurrenthashmap-hashtable-和-synchronized-map-in-java/](https://www.geeksforgeeks.org/difference-between-concurrenthashmap-hashtable-and-synchronized-map-in-java/)

在这里，我们将一个接一个地讨论，然后在充分理解这三者之后，再讨论它们的区别。我们将首先讨论并发哈希表，然后讨论哈希表，最后讨论同步映射。让我们首先从 ConcurrentHashMap 开始。

[ConcurrentHashMap](https://www.geeksforgeeks.org/concurrenthashmap-in-java/) 的底层数据结构是 [HashTable](https://www.geeksforgeeks.org/hashtable-in-java/) 。ConcurrentHashMap 允许并发读取和线程安全更新操作。执行读操作的线程不需要任何锁，但是执行更新操作的线程需要一个锁，但是它只是 Map 的一个特定部分的锁(桶级锁)。而不是通过将地图内部分成由并发级别定义的较小部分来实现整个地图的并发更新。默认并发级别为 16，即 ConcurrentHashMap 允许同时进行读取和 16 个写入(更新)操作。键和值都不允许值 null。当一个线程迭代时，另一个线程可以执行更新操作，并且 ConcurrentHashMap 从不抛出 ConcurrentModificationException。

**语法:**

```
ConcurrentHashMap<K,V> CHM = new  ConcurrentHashMap<>();
```

上面的构造函数使用创建一个空的 ConcurrentHashMap

*   默认初始容量等于 16
*   默认填充比等于 0.75
*   默认并发级别 16，其中 K 是键，V 是 ConcurrentHashMap 的值

**示例:**

## Java

```
// Java program to illustrate ConcurrentHashMap

// Importing required packages
import java.io.*;
import java.util.*;
import java.util.concurrent.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating ConcurrentHashMap class object
        // Declaring object of integer an string type
        ConcurrentHashMap<Integer, String> chm
            = new ConcurrentHashMap<>();

        // Adding entry to ConcurrentHashMap
        // Custom input entries
        chm.put(65, "A");
        chm.put(66, "B");

        // Print and display the ConcurrentHashMap
        System.out.println(chm);

        // Adding the entry if the given entry is not
        // present in the ConcurrentHashMap Custom input
        // entries
        chm.putIfAbsent(67, "C");
        chm.putIfAbsent(68, "D");

        // Printand display the ConcurrentHashMap
        System.out.println(chm);

        // Removing entry With Key and Value as 68 and D
        chm.remove(68, "D");

        // Print and display the ConcurrentHashMap
        System.out.println(chm);

        // Replacing  Value of an entry
        chm.replace(66, "B", "E");

        // Again, print and display the ConcurrentHashMap
        System.out.println(chm);
    }
}
```

**输出**

```
{65=A, 66=B}
{65=A, 66=B, 67=C, 68=D}
{65=A, 66=B, 67=C}
{65=A, 66=E, 67=C}
```

**现在细想第二个概念就是** [**哈希表**](https://www.geeksforgeeks.org/hashtable-in-java/) **。**哈希表的底层数据结构是哈希表。HashTable 中的插入顺序不会被保留，它是基于键的 hashcode。不允许重复键，但值可以重复。键和值都允许使用异构对象。键和值都不允许为空值，否则我们将得到 RunTimeException，表示 NullPointerException。它实现了可序列化和可克隆的接口，但没有实现随机访问。其中的每个方法都是同步的，因此哈希表对象是线程安全的。如果我们频繁的操作是搜索操作，HashTable 是最好的选择。

**语法:**

```
Hashtable<K,V> ht = new Hashtable<>();
```

上面的构造函数创建了一个空哈希表对象，初始默认容量为 11，默认填充比为 0.75。其中 K 是键，V 是哈希表的值。

**示例:**

## Java

```
// Java program to illustrate HashTable

// Importing required packages
import java.io.*;
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating Hashtable object
        Hashtable<Integer, String> ht = new Hashtable<>();

        // Adding entry to Hashtable
        // Custom input entries
        ht.put(65, "A");
        ht.put(66, "B");
        ht.put(67, "C");
        ht.put(68, "D");

        // Print and display the HashTable elements
        System.out.println(ht);
    }
}
```

**输出**

```
{65=A, 68=D, 67=C, 66=B}
```

**最后，讨论出** [**【同步地图】**](https://www.geeksforgeeks.org/collections-synchronizedmap-method-in-java-with-examples/) **之后，降落在他们三人之间的决定性分歧**上。synchronizedMap()方法用于返回由指定映射支持的同步(线程安全)映射。这个方法存在于 java.util.Collections 中。

**语法:**

```
public static <K,V> Map<K,V> synchronizedMap(Map<K,V> M)

// where M is the map to be synchronized K is key 
//   and V is value for the resultant synchronized map.    
```

**示例:**

## Java

```
// Java program to demonstrate synchronizedMap() method

// Importing required packages
import java.io.*;
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Try block to check for exceptions
        try {

            // Creating object of HashMap
            // Declaring object of integer and string type
            HashMap<Integer, String> map = new HashMap<>();

            // Adding entry to map object created above
            // Custom input entries
            map.put(65, "A");
            map.put(66, "B");
            map.put(67, "C");
            map.put(68, "D");

            // Print and display the map object
            System.out.println("Map is " + map);

            // Creating a synchronized map object
            // Declaring object of type integer and string
            Map<Integer, String> synmap
                = Collections.synchronizedMap(map);

            // Print and display the synchronized map
            // elements
            System.out.println("Synchronized map is : "
                               + synmap);
        }

        // Catch block to handle the exceptions
        catch (IllegalArgumentException e) {

            // Display the exception on the console
            System.out.println(e);
        }
    }
}
```

**输出**

```
Map is {65=A, 66=B, 67=C, 68=D}
Synchronized map is : {65=A, 66=B, 67=C, 68=D}
```

到目前为止，我们已经讨论了足够多的概念以及程序中的内部工作实现。让我们最后总结一下它们之间的区别，以便更好地理解它们之间的细微差别。

<figure class="table">

| **ConcurrentHashMap** | **同步地图** | **HashTable** |
| --- | --- | --- |
| 我们只需用一个桶级锁就可以在不锁定总地图对象的情况下获得线程安全。 | 我们将通过锁定整个地图对象来获得线程安全。 | 我们将通过锁定整个地图对象 |
| 来获得线程安全，一次允许多个线程对地图对象进行安全操作。 | 一次只允许一个线程对一个地图对象执行任何操作。 | 一次允许一个线程对一个地图对象进行操作。 |
| 读操作可以在没有锁的情况下执行，但写操作可以在存储桶级锁的情况下执行。 | 每次读写操作需要总图对象 | 每次读写操作需要总图对象 |
| 当一个线程迭代地图对象时，另一个线程被允许修改地图，不会得到 concurrentmodification exception。 | 当一个线程迭代映射对象时，其他线程不允许修改映射，否则我们将获得 ConcurrentModificationException | 当一个线程迭代映射对象时，其他线程不允许修改映射，否则我们将获得 ConcurrentModificationException |
| ConcurrentModificationException | 键和值都允许 Null | 键和值都不允许 Null。 |
| 引入 java 1.2 版本 | 引入 java 1.2 版本 | 引入 java 1.2 版本 |

</figure>