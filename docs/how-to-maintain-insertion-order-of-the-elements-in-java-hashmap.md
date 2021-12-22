# 如何维护 Java HashMap 中元素的插入顺序？

> 原文:[https://www . geesforgeks . org/如何维护 java 中元素的插入顺序-hashmap/](https://www.geeksforgeeks.org/how-to-maintain-insertion-order-of-the-elements-in-java-hashmap/)

当元素从[哈希映射](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)中获取时，由于哈希，它们插入的顺序在检索时不会得到维护。我们可以使用 LinkedHashMap 实现给定的任务。[链接哈希表](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/)类实现了一个双向链表，这样它就可以遍历所有的元素。

**示例:**

```java
Input : HashMapInput = {c=6, a=1, b=2}
Output: HashMapPrint = {c=6, a=1, b=2}

Input : HashMapInput = {"first"=1, "second"=3}
Output: HashMapPrint = {"first"=1, "second"=3}
```

**语法:**

> **公共链接哈希表(地图 m)**

它创建一个 LinkedHashMap 类的对象，该对象具有在原始 Map 对象中指定的相同映射。

**此处不维护订单:**哈希映射实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to maintain insertion order
// of the elements in HashMap

// Using HashMap (Order not maintain)
import java.io.*;
import java.util.*;
class GFG {

    public static void main(String args[])
    {

        // creating a hashmap
        HashMap<String, String> hm = new HashMap<>();

        // putting elements
        hm.put("01", "aaaaaaa");
        hm.put("03", "bbbbbbb");
        hm.put("04", "zzzzzzz");
        hm.put("02", "kkkkkkk");

        System.out.println("Iterate over original HashMap");

        // printing hashmap
        for (Map.Entry<String, String> entry :
             hm.entrySet()) {
            System.out.println(entry.getKey() + " => "
                               + ": " + entry.getValue());
        }
    }
}
```

**Output**

```java
Iterate over original HashMap
01 => : aaaaaaa
02 => : kkkkkkk
03 => : bbbbbbb
04 => : zzzzzzz
```

这里，HashMap 的原始插入顺序是[01，03，04，02]，但输出不同[01，02，03，04]。它没有保持元素的原始插入顺序。

**此处维护秩序:**链接 HashMap 实现

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to maintain insertion order
// of the elements in HashMap

// LinkedHashMap
import java.io.*;
import java.util.*;
class GFG {

    public static void main(String args[])
    {

        // creating a hashmap
        HashMap<String, String> hm = new LinkedHashMap<>();

        // putting elements
        hm.put("01", "aaaaaaa");
        hm.put("03", "bbbbbbb");
        hm.put("04", "zzzzzzz");
        hm.put("02", "kkkkkkk");

        // printing LinkedHashMap
        System.out.println("Iterate over LinkedHashMap");
        for (Map.Entry<String, String> entry :
             hm.entrySet()) {
            System.out.println(entry.getKey() + " => "
                               + ": " + entry.getValue());
        }
    }
}
```

**Output**

```java
Iterate over LinkedHashMap
01 => : aaaaaaa
03 => : bbbbbbb
04 => : zzzzzzz
02 => : kkkkkkk
```