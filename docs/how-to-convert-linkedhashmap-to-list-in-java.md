# 如何在 Java 中将 LinkedHashMap 转换为 List？

> 原文:[https://www . geesforgeks . org/how-convert-link edhashmap-to-list-in-Java/](https://www.geeksforgeeks.org/how-to-convert-linkedhashmap-to-list-in-java/)

[LinkedHashMap](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 是 Java 中的预定义类，类似于 HashMap，包含 key 及其各自的值不同于 HashMap，在 LinkedHashMap 中插入顺序是保留的。

我们需要将 LinkedHashMap 转换为 ArrayList。映射将数据存储在键和值对中，同时将链接哈希表转换为数组列表我们将把映射的键存储在一个单独的列表中，类似地将值存储在另一个列表中，为了更好地理解，请看示例和算法。

**示例:**

```java
Input : { 1 = 3, 4 = 2, 6 = 5, 2 = 1 }

output : Key   -> [ 1, 4, 6, 2 ]
         value -> [ 3, 2, 5, 1]

Input : { 2 = 10, 4 = 4, 6 = 23, 8 = 12 }

output : Key   -> [ 2, 4, 6, 6 ]
         value -> [ 10, 4, 23, 12]
```

**算法:**

*   在链接哈希表
    中使用 For/while 循环进行迭代
*   为键及其受尊重的值获取两个不同的数组列表。

*   现在迭代 LinkedhashMap 中的 for-Each 循环，并用它们定义的数组列表添加键和值

**伪代码:**

```java
for (Map.Entry<Object, Object> it : l.entrySet()) {
            l1.add(it.getKey());
            l2.add(it.getValue());
}

Here, l is LinkedHashMap
      l1 is Arraylist for keys
      l2 is Arraylist for Values
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to convert LinkedHashMap
// to List

import java.util.*;
import java.io.*;

class GFG {

    public static void main(String[] args)
    {
        LinkedHashMap<Object, Object> l = new LinkedHashMap<>();

        l.put(2, 5);
        l.put(4, 6);
        l.put(5, 16);
        l.put(6, 63);
        l.put(3, 18);

          // Taking two ArrayList
        ArrayList<Object> l1 = new ArrayList<>();

        ArrayList<Object> l2 = new ArrayList<>();

        for (Map.Entry<Object, Object> it : l.entrySet()) {
            l1.add(it.getKey());
            l2.add(it.getValue());
        }

        System.out.print("Key -> ");
        System.out.println(l1);
        System.out.print("Value -> ");
        System.out.println(l2);
    }
}
```

**Output**

```java
Key -> [2, 4, 5, 6, 3]
Value -> [5, 6, 16, 63, 18]
```

**时间复杂度:** O(n)