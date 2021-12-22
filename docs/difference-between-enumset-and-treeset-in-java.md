# Java 中枚举集和树集的区别

> 原文:[https://www . geesforgeks . org/enum set 和-treeset-in-java 的区别/](https://www.geeksforgeeks.org/difference-between-enumset-and-treeset-in-java/)

枚举集和树集都是在[集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)中定义的类。但是他们之间几乎没有什么区别。在本文中，我们试图涵盖它们之间的所有这些差异。

**1。** [**枚举**](https://www.geeksforgeeks.org/enumset-class-java/) **:** 枚举是为[枚举类型](https://www.geeksforgeeks.org/enum-in-java/)设置[接口的专门实现。它扩展了抽象集，并在 Java 中实现了集合接口。EnumSet 的几个要点如下:](https://www.geeksforgeeks.org/set-in-java/)

[](https://www.geeksforgeeks.org/set-in-java/)
*   [枚举类是](https://www.geeksforgeeks.org/set-in-java/) [Java 集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的成员,不同步。
*   All elements in an enumeration set must come from a single [enumeration type](https://www.geeksforgeeks.org/enum-in-java/) , which is specified when the set is created explicitly or implicitly.

 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 

*   Enumeration does not allow insertion of null objects. If we try to insert a null object, it will throw **nullpointerexception** .
*   It uses a **fail-safe** iterator, so if the set is modified during iteration, it won't throw **concurrentmodification exception** .

**例:**

## 爪哇

```java
// Java program to demonstrate
// the EnumSet

import java.util.*;
class enumSetExample {
    enum Colors {
        Red,
        Pink,
        Grey,
        Yellow,
        Green
    }
    public static void main(String args[])
    {

        // Creating an EnumSet
        EnumSet<Colors> colors
            = EnumSet.of(Colors.Pink, Colors.Green);

        Iterator<Colors> itr = colors.iterator();

        // Iterate and print elements to
        // the console
        System.out.println("EnumSet : ");
        while (itr.hasNext()) {
            System.out.println(itr.next());
        }
    }
}
```

**输出**

```java
EnumSet : 
Pink
Green
```