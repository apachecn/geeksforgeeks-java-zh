# 打印链接哈希表值的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-print-linked hashmap-values/](https://www.geeksforgeeks.org/java-program-to-print-linkedhashmap-values/)

[LinkedHashMap](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 是 Java 中的一个预定义类，类似于 HashMap，包含 key 及其各自的值与 HashMap 不同，在 LinkedHashMap 中保留插入顺序。我们需要打印散列图的值，该值与其关键字相链接。我们必须遍历 LinkedHashMap 中的每个键，并使用 for 循环打印其各自的值。

**例:**

```
Input:

Key- 2 : Value-5
Key- 4 : Value-3
Key- 1 : Value-10
Key- 3 : Value-12
Key- 5 : Value-6

Output: 5, 3, 10, 12, 6
```

**算法:**

*   Use **for-loop through the LinkedHashMap every** .
*   Using the **entryset ()** method, this method gives the set structure of all maps for traversing the whole map. Print their respective values for each iteration.

**示例:**

## Java

```
// Java program to print all the values
// of the LinkedHashMap

import java.util.*;
import java.io.*;

class GFG {
    public static void main (String[] args) {

      LinkedHashMap<Integer,Integer> LHM = new LinkedHashMap<>();

      LHM.put(2,5);
      LHM.put(4,3);
      LHM.put(1,10);
      LHM.put(3,12);
      LHM.put(5,6);

      // using .entrySet() which gives us the 
      // list of mappings of the Map
      for(Map.Entry<Integer,Integer>it:LHM.entrySet())
          System.out.print(it.getValue()+", ");
    }
}
```

**输出**

```
5, 3, 10, 12, 6,
```

**时间复杂度:** O(n)。