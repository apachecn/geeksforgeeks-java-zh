# 如何在 Java 中获取 LinkedHashMap 的所有值？

> 原文:[https://www . geesforgeks . org/如何获取 java 中 linkedhashmap 的所有值/](https://www.geeksforgeeks.org/how-to-get-all-the-values-of-the-linkedhashmap-in-java/)

[LinkedHashMap](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 是 Java 中的一个预定义类，类似于 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) ，包含 key 及其各自的值，不像 HashMap。在 LinkedHashMap 中，插入顺序被保留。任务是获取我们的 LinkedHashMap 中存在的所有值，这些值与它们各自的键相链接。使用迭代或预定义函数获取所有值。

**示例:**

```
Input : Key-> 5 : Value->4
    Key-> 8 : Value->2
    Key-> 6 : Value->20
    Key-> 9 : Value->18
    Key-> 1 : Value->66

Output:

Values : [4, 2, 20, 18, 66]
```

**方法 1:**

使用 [for-each](https://www.geeksforgeeks.org/for-each-loop-in-java/) 循环在每次迭代后遍历我们的 LinkedHashMap，并将相应键的值存储在列表中。将所有值存储在列表中后，打印列表。

**伪码:**

```
for (Map.Entry<Integer, Integer> i : LHM.entrySet()) {
            list.add(i.getValue());
}
```

这里，LHM 是 LinkedHashMap 的名字。名单是我们名单的名字。

**语法:**

```
hash_map.entrySet()
```

**返回值:**该方法返回一个与哈希映射具有相同元素的集合。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to get all the values of the LinkedHashMap

import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // create an instance of linked hashmap
        LinkedHashMap<Integer, Integer> LHM
            = new LinkedHashMap<>();

        // Add mappings
        LHM.put(5, 4);
        LHM.put(8, 2);
        LHM.put(6, 20);
        LHM.put(9, 18);
        LHM.put(1, 66);

        List<Integer> list = new ArrayList<>();

        // Add the values to a list
        for (Map.Entry<Integer, Integer> i :
             LHM.entrySet()) {
            list.add(i.getValue());
        }

        System.out.println("values : " + list);
    }
}
```

**Output**

```
values : [4, 2, 20, 18, 66]
```

**时间复杂度:** O(n)

**接近 2**

这种方法是解决我们的问题的最佳方法，即获取 LinkedHashMap 的所有值。在上面的方法中，我们使用迭代来获得所有的值。在这种方法中，我们使用预定义的方法来获取我们的 LinkedHashMap 的相应键的值。

使用预定义的方法来存储我们的 LinkedHashMap 中每个键的所有值。将所有值存储在列表中后，打印列表。

**伪码:**

```
Collection<Integer> values = LHM.values();
```

这里， **LHM** 是 LinkedHashMap 值的名称，是包含所有值的列表的名称。

**语法:**

```
Hash_Map.values()
```

**返回值:**该方法用于返回包含地图所有值的集合视图。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to get all the values of the LinkedHashMap

import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // create an instance of linked hashmap
        LinkedHashMap<Integer, Integer> LHM
            = new LinkedHashMap<>();

        // Add mappings
        LHM.put(5, 4);
        LHM.put(8, 2);
        LHM.put(6, 20);
        LHM.put(9, 18);
        LHM.put(1, 66);

        // get the values of the map
        Collection<Integer> values = LHM.values();

        // print the values list
        System.out.println("values : " + values);
    }
}
```

**Output**

```
values : [4, 2, 20, 18, 66]
```

**时间复杂度** : O(1)。

由[值()](https://www.geeksforgeeks.org/hashmap-values-method-in-java/)方法返回的集合视图由原始的 LinkedHashMap 对象支持。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to get all the values of the LinkedHashMap

import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // create an instance of linked hashmap
        LinkedHashMap<Integer, Integer> LHM
            = new LinkedHashMap<>();

        // Add mappings
        LHM.put(5, 4);
        LHM.put(8, 2);
        LHM.put(6, 20);
        LHM.put(9, 18);
        LHM.put(1, 66);

        // get the collection of values
        Collection<Integer> values = LHM.values();

        // remove a mapping
        values.remove(20);

        // print the values collection
        System.out.println("values : " + values);

        // print Linked hashmap
        System.out.println("LinkedHashMap : " + LHM);

        // Add mapping
        LHM.put(10, 9);

        // print values collection
        System.out.println("values : " + values);

        // print linked hash map
        System.out.println("LinkedHashMap : " + LHM);
    }
}
```

**Output**

```
values : [4, 2, 18, 66]
LinkedHashMap : {5=4, 8=2, 9=18, 1=66}
values : [4, 2, 18, 66, 9]
LinkedHashMap : {5=4, 8=2, 9=18, 1=66, 10=9}
```