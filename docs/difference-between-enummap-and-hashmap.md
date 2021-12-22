# 枚举映射和哈希映射的区别

> 原文:[https://www . geesforgeks . org/enummap 和-hashmap 之间的差异/](https://www.geeksforgeeks.org/difference-between-enummap-and-hashmap/)

EnumMap 和 HashMap 都是实现[映射](https://www.geeksforgeeks.org/map-interface-java-examples/)接口的类。但是它们之间存在一些差异。所以我们试图列出 EnumMap 和 HashMap 之间的区别。

**1。**[**EnumMap**](https://www.geeksforgeeks.org/enummap-class-java-example/)**:**EnumMap 是 [地图界面](https://www.geeksforgeeks.org/map-interface-java-examples/) 为 [枚举类型](https://www.geeksforgeeks.org/enum-in-java/) 的专门实现。它扩展了 [抽象地图](https://www.geeksforgeeks.org/abstractmap-in-java/) ，在 Java 中实现了 [地图](https://www.geeksforgeeks.org/map-interface-java-examples/) 界面。EnumMap 的几个要点如下:

*   EnumMap 类是 [Java 集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的成员,不同步。
*   EnumMap is an ordered collection, which is maintained according to the natural order of its keys (the natural order of keys refers to the order in which enum constants are declared inside enum types).
*   帐号 T0 散列图 T1 .
*   All keys of each EnumMap instance must be keys of the same enumeration type.
*   EnumMap does not allow the insertion of empty keys. If we try to insert empty keys, it will throw **nullpointerexception** .
*   EnumMap is internally represented as an array, so the performance is better.

**列举图演示:**

## 【Java】

```
// Java program to illustrate working
// of EnumMap

import java.util.*;

class EnumMapExample {

    public enum Days {
        Sunday,
        Monday,
        Tuesday,
        Wendensday;
    }

    public static void main(String[] args)
    {
        // Creating an EnumMap of the Days enum
        EnumMap<Days, Integer> enumMap
            = new EnumMap<>(Days.class);

        // Insert using put() method
        enumMap.put(Days.Sunday, 1);
        enumMap.put(Days.Monday, 2);
        enumMap.put(Days.Tuesday, 3);
        enumMap.put(Days.Wendensday, 4);

        // Printing size of EnumMap
        System.out.println("Size of EnumMap: "
                           + enumMap.size());
        // Printing the EnumMap
        for (Map.Entry m : enumMap.entrySet()) {
            System.out.println(m.getKey() + " "
                               + m.getValue());
        }
    }
}
```

输出

```
Size of EnumMap: 4
Sunday 1
Monday 2
Tuesday 3
Wendensday 4
```