# 将 HashMap 转换为 Java 中的 linked list

> 原文:[https://www . geesforgeks . org/convert-hashmap-to-linked list-in-Java/](https://www.geeksforgeeks.org/convert-hashmap-to-linkedlist-in-java/)

[HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) 与 [HashTable](https://www.geeksforgeeks.org/hashtable-in-java/) 相似，但不同步。它也允许存储空键，但是应该只有一个空键对象，并且可以有任意数量的空值。

[链接列表](https://www.geeksforgeeks.org/linked-list-in-java/)是 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中的集合框架的一部分。这个类是 LinkedList 数据结构的实现，它是一个线性数据结构，其中元素不存储在连续的位置，每个元素都是一个独立的对象，有数据部分和地址部分。这些元素使用指针和地址进行链接。每个元素都被称为一个节点。

**示例:**

```
Input:    
    l.put(2, 5);
    l.put(3, 6);
    l.put(4, 1);
    l.put(8, 2);

Output:    
    LinkedList of key-> [2, 3, 4, 8]
    LinkedList of values-> [5, 6, 1, 2]
    respectively the output for key and values.
```

**键集()方法的语法**

```
hash_map.keySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个具有哈希映射键的集合。

**值的语法()方法**

```
Hash_Map.values()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法用于返回包含地图所有值的集合视图。

PSU 代码

```
List<Integer> list = new LinkedList<>(l.keySet());
List<Integer> listOfValue = new LinkedList<>(l.values());
```

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java progaram to Convert HashMap to LinkedList

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // create a hashmap instance
        HashMap<Integer, Integer> l = new HashMap<>();

        // add mappings
        l.put(2, 5);
        l.put(3, 6);
        l.put(4, 1);
        l.put(8, 2);

        // list of keys
        List<Integer> list = new LinkedList<>(l.keySet());

        // list of values
        List<Integer> listOfValue
            = new LinkedList<>(l.values());

        // print the list
        System.out.println("LinkedList of key-> " + list);
        System.out.println("LinkedList of values-> "
                           + listOfValue);
    }
}
```

**Output**

```
LinkedList of key-> [2, 3, 4, 8]
LinkedList of values-> [5, 6, 1, 2]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java progaram to Convert HashMap to LinkedList 

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    { 
          // create a hashmap instance
        HashMap<Integer, String> l = new HashMap<>();

        // add mappings
        l.put(1, "Geeks");
        l.put(4, "For");
        l.put(3, "Geeks");

        // list of keys
        List<Integer> list = new LinkedList<>(l.keySet());

        // list of values
        List<String> listOfValue
            = new LinkedList<>(l.values());

        // print the list
        System.out.println("LinkedList of key-> " + list);
        System.out.println("LinkedList of values-> "
                           + listOfValue);
    }
}
```

**Output**

```
LinkedList of key-> [1, 3, 4]
LinkedList of values-> [Geeks, Geeks, For]
```