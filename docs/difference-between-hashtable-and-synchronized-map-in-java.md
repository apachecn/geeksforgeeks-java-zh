# Java 中哈希表和同步映射的区别

> 原文:[https://www . geesforgeks . org/Java 中 hashtable 和 synchronized-map 的区别/](https://www.geeksforgeeks.org/difference-between-hashtable-and-synchronized-map-in-java/)

[哈希表](https://www.geeksforgeeks.org/hashtable-in-java/)类实现了一个哈希表，它将键映射到值。任何非空对象都可以用作键或值。为了成功地从哈希表中存储和检索对象，用作键的对象必须实现 hashCode 方法和 equals 方法。

**哈希表的特点:**

*   It's a bit like a hash table, but it's synchronous.
*   Hash table stores key/value pairs in the hash table.
*   In the hash table, we specify an object to be used as a key and the value we want to associate with the key. Then, the key is hashed, and the obtained hash code is used as the index for storing the value in the table.
*   The initial default capacity of hash table class is 11, and the loading factor is 0.75.
*   HashMap does not provide any Enumeration, while Hashtable does not provide fast invalidation enumeration.

**例:**

## 爪哇

```
// Java program to demonstrate the
// usage of HashTable

import java.util.*;
class Hashtable1 {
    public static void main(String args[])
    {
        // Creating a HashTable
        Hashtable<Integer, String> mytable = new Hashtable<Integer, String>();

        // Adding elements to HashTable
        mytable.put(1, "James Bond");
        mytable.put(2, "Donald Trumph");
        mytable.put(3, "Joe Biden");
        mytable.put(4, "Mona Lisa");

        // Iterating through HashTable
        for (Map.Entry m : mytable.entrySet()) 
        {
            System.out.println(m.getKey() + " "
                               + m.getValue());
        }
    }
}
```

**输出**

```
4 Mona Lisa
3 Joe Biden
2 Donald Trumph
1 James Bond
```