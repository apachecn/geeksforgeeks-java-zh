# 如何在 Java 中将 LinkedHashMap 转换成两个数组？

> 原文:[https://www . geesforgeks . org/how-convert-link edhashmap-to-two-array-in-Java/](https://www.geeksforgeeks.org/how-to-convert-linkedhashmap-to-two-arrays-in-java/)

[LinkedHashMap](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 是 java 中的一个预定义类，类似于 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) 。LinkedHashMap 和 HashMap 的唯一区别是 LinkedHashMap 保留插入顺序，而 HashMap 不保留插入顺序。LinkedHashMap 可以在 java 中转换成两个 array，其中一个 array 用于 LinkedHashMap 中的键，另一个 array 用于 Values。

**例:**

```java
Input : LinkedHashMap = [2=6, 3=4, 5=7, 4=6]
Output:
Array of keys = [2, 3, 5, 4]
Array of Values = [6, 4, 7, 6]

Input : LinkedHashMap = [1=a, 2=b, 3=c, 4=d]
Output:
Array of keys = [1, 2, 3, 4]
Array of Values = [a, b, c, d]
```

**算法:**

1.  Enter in the LinkedHashMap with keys and respective values.
2.  Create an array with the same data type as the key in LinkedHashMap.
3.  Create another array with the same data type as the value in LinkedHashMap.
4.  开始 LinkedHashMap 遍历。
5.  Copy each key and value in two arrays.
6.  After traversing, print two arrays.

下面是上述方法的实现:

T3】JavaT5

```java
// Java Program to Convert LinkedHashMap to Two Arrays
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        LinkedHashMap<Integer, Integer> lhm
            = new LinkedHashMap<>();

        lhm.put(2, 6);
        lhm.put(3, 4);
        lhm.put(5, 7);
        lhm.put(4, 6);
        lhm.put(6, 8);

        Integer[] Keys = new Integer[lhm.size()];

        Integer[] Values = new Integer[lhm.size()];
        int i = 0;

        // Using for-each loop
        for (Map.Entry mapElement : lhm.entrySet()) {
            Integer key = (Integer)mapElement.getKey();

            // Add some bonus marks
            // to all the students and print it
            int value = ((int)mapElement.getValue());

            Keys[i] = key;
            Values[i] = value;
            i++;
        }

        // printing all the element of array contain keys
        System.out.print("Array of Key -> ");
        for (Integer key : Keys) {
            System.out.print(key + ", ");
        }

        // iterate value array
        System.out.println();
        System.out.print("Array of Values -> ");
        for (Integer value : Values) {
            System.out.print(value + ", ");
        }
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(n)