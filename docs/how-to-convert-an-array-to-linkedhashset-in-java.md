# 如何在 Java 中将数组转换为 LinkedHashSet？

> 原文:[https://www . geesforgeks . org/如何将数组转换为 java 中的 link edhashset/](https://www.geeksforgeeks.org/how-to-convert-an-array-to-linkedhashset-in-java/)

[数组](https://www.geeksforgeeks.org/introduction-to-arrays/)是存储在连续存储位置的项目的集合。根据数组的定义，数组可以包含基元数据类型以及类的对象。而[链接哈希集](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/)只包含唯一的元素，它们以插入的相同顺序存储。

**例:**

```
Input: arr = {"A", "B", "C", "D", "A"}
Output: LinkedHashSet = {"A", "B", "C", "D"}
LinkedHashSet does not contain repeated elements.

Input: arr = {1, 3, 5, 3, 1}
Output: LinkedHashset = {1, 3, 5}
```

*有几种方法可以将数组转换为 Java 中 LinkedHashSet 的对象，如下所示:*

**1。使用** [**作为列表**](https://www.geeksforgeeks.org/arrays-aslist-method-in-java-with-examples/) **方法和链接 HashSet 构造函数**

*   The linked HashSet class provides a constructor that accepts collection objects.
*   But to use it, we need to use the asList method of the Arrays class to convert the array into a List.

## Java

```
// Java program to convert an array to LinkedHashSet

import java.util.Arrays;
import java.util.LinkedHashSet;
import java.util.Set;

public class ArrayToLinkedHashSet {

    public static void main(String[] args)
    {

        // array of string
        String[] names
            = { "John", "Devid", "Smith", "Joe", "Stark" };

        // First convert the name array to List and then
        // use the LinkedHashSet constructor to convert
        // array to linkedhasset

        Set<String> linkedhasset_name
            = new LinkedHashSet<String>(Arrays.asList(names));

        System.out.println(
            "LinkedHashSet contains element: " + linkedhasset_name);
    }
}
```

**输出**

```
LinkedHashSet contains element: [John, Devid, Smith, Joe, Stark]
```