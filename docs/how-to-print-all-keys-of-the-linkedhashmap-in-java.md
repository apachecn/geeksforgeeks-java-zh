# 如何用 Java 打印 LinkedHashMap 的所有键？

> 原文:[https://www . geesforgeks . org/如何在 java 中打印 linkedhashmap 的所有密钥/](https://www.geeksforgeeks.org/how-to-print-all-keys-of-the-linkedhashmap-in-java/)

[LinkedHashMap](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 是 Java 中的一个预定义类，类似于 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) ，包含一个键及其各自的值。与 HashMap 不同，In LinkedHashMap 的插入顺序是保留的。任务是用 java 打印我们的 LinkedHashMap 中存在的所有键。我们必须遍历链接哈希表中的每个键并打印出来。

**示例:**

```
Input : Key- 1  : Value-5
    Key- 29 : Value-13
    Key- 14 : Value-10
    Key- 34 : Value-2
    Key- 55 : Value-6

Output: 1, 29, 14, 34, 55
```

**方法 1:** 使用[for-每个](https://www.geeksforgeeks.org/for-each-loop-in-java/)循环迭代**链接的哈希表**。对于每次迭代，我们使用 **getKey()** 方法打印各自的密钥。

```
for(Map.Entry<Integer,Integer>ite : LHM.entrySet())
    System.out.print(ite.getKey()+", ");
```

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to print all keys of the LinkedHashMap

import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
          // create a linkedhashmap
        LinkedHashMap<Integer, Integer> LHM
            = new LinkedHashMap<>();

          // Add mappings
        LHM.put(1, 5);
        LHM.put(29, 13);
        LHM.put(14, 10);
        LHM.put(34, 2);
        LHM.put(55, 6);

          // print keys using getKey() method
        for (Map.Entry<Integer, Integer> ite :
             LHM.entrySet())
            System.out.print(ite.getKey() + ", ");
    }
}
```

**Output**

```
1, 29, 14, 34, 55,
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to print all keys of the LinkedHashMap

import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // create a linkedhashmap
        LinkedHashMap<String, String> LHM
            = new LinkedHashMap<>();

        // Add mappings
        LHM.put("Geeks", "Geeks");
        LHM.put("for", "for");
        LHM.put("Geeks", "Geeks");

        // print keys using getKey() method
        for (Map.Entry<String, String> ite : LHM.entrySet())
            System.out.print(ite.getKey() + ", ");
    }
}
```

**Output**

```
Geeks, for,
```

**方法二:(使用** [键集()](https://www.geeksforgeeks.org/hashmap-keyset-method-in-java/) **方法)**

**语法:**

```
hash_map.keySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个具有哈希映射键的集合。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // create an instance of linked hashmap
        LinkedHashMap<String, String> lhm
            = new LinkedHashMap<String, String>();

        lhm.put("One", "Geeks");
        lhm.put("Two", "For");
        lhm.put("Three", "Geeks");

        // get all keys using the keySet method
        Set<String> allKeys = lhm.keySet();

        // print keys
        System.out.println(allKeys);
    }
}
```

**Output**

```
[One, Two, Three]
```