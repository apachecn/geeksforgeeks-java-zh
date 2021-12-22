# 使用 Java 中的迭代器迭代 LinkedHashMap】

> 原文:[https://www . geeksforgeeks . org/iterate-through-link edhashmap-使用 java 中的迭代器/](https://www.geeksforgeeks.org/iterate-through-linkedhashmap-using-an-iterator-in-java/)

[LinkedHashMap](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 是 java 中的一个预定义类，类似于 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) 。LinkedHashMap 和 HashMap 的唯一区别是 LinkedHashMap 保留插入顺序，而 HashMap 不保留插入顺序。任务是使用迭代器迭代链接的哈希表。我们使用 Iterator 对象来迭代一个 LinkedHashMap。

**例**T0】

**算法:**

1.创建一个链接哈希表并添加键、值对。

2.我们使用

```java
Set s = lhm.entrySet();
```

将链接的哈希表转换为 [entrySet](https://www.geeksforgeeks.org/hashmap-entryset-method-in-java/)

3.我们为集合定义迭代器。

```java
Iterator it=s.iterator();

```

4.使用 while 循环，我们遍历我们的 linkedHashMap。

```java
while(it.hasNext())                      
     System.out.println(it.next()); 
```

**实现**

T5】Java

```java
// Java program to Iterate through LinkedHashMap using an
// Iterator

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // create a linkedhashmap
        LinkedHashMap<Integer, Integer> lhm
            = new LinkedHashMap<>();

        // add mappings
        lhm.put(2, 6);
        lhm.put(3, 4);
        lhm.put(6, 8);
        lhm.put(4, 10);
        lhm.put(5, 6);

        // create an entryset
        Set s = lhm.entrySet();

        // create an iterator
        Iterator it = s.iterator();

        // iterate an print the mappings
        System.out.println("key=Value");
        while (it.hasNext()) {
            System.out.println(it.next());
        }
    }
}
```

**输出**

```java
key=Value
2=6
3=4
6=8
4=10
5=6
```

**时间复杂度:** O(n)。