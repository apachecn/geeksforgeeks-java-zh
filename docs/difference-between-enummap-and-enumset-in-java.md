# Java 中 EnumMap 和 EnumSet 的区别

> 原文:[https://www . geesforgeks . org/enummap-和-enumset-in-java/](https://www.geeksforgeeks.org/difference-between-enummap-and-enumset-in-java/) 之间的区别

EnumMap 和 EnumSet 都是 java [集合](https://www.geeksforgeeks.org/collections-in-java-2/)中定义的类。在本文中，我们将学习 EnumMap 和 EnumSet 之间的区别。EnumMap 是[地图](https://www.geeksforgeeks.org/map-interface-java-examples/)界面的专门实现，EnumSet 是 [Set](https://www.geeksforgeeks.org/set-in-java/) 界面的专门实现。他们之间存在一些差异。所以我们试图列出 EnumMap 和 EnumSet 之间的区别。

[**1。EnumMap**](https://www.geeksforgeeks.org/enummap-class-java-example/)**:EnumMap 是[映射接口](https://www.geeksforgeeks.org/map-interface-java-examples/)对[枚举类型](https://www.geeksforgeeks.org/enum-in-java/)的专门实现。实现了[映射](https://www.geeksforgeeks.org/map-interface-java-examples/)接口，用 Java 扩展了抽象映射。**

***   帐号 T0 散列图 T1 .*   EnumMap class is a member of [Java collection framework](https://www.geeksforgeeks.org/collections-in-java-2/) .*   EnumMap is an ordered collection that is maintained according to the natural order of their keys.*   All keys of each enumeration instance must be keys of the same [enumeration](https://www.geeksforgeeks.org/enum-in-java/) type.*   EnumMap does not allow the insertion of empty keys. If we try to insert empty keys, **nullpointerexception** will be thrown.*   EnumMap is internally expressed as an array for better performance.**

下面是 EnumMap 的实现:

## Java

```
// Java program to illustrate working of EnumMap

import java.util.*;

class EnumMapExample {

    public enum Fruits {
        Apple,
        Mango,
        Orange,
        Banana;
    }

    public static void main(String[] args)
    {
        // Creating an EnumMap of the Fruits enum
        EnumMap<Fruits, Integer> enumMap
            = new EnumMap<>(Fruits.class);

        // Insert using put() method
        enumMap.put(Fruits.Apple, 1);
        enumMap.put(Fruits.Mango, 2);
        enumMap.put(Fruits.Orange, 3);
        enumMap.put(Fruits.Banana, 4);

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
Apple 1
Mango 2
Orange 3
Banana 4
```