# Java 中的抽象集合 toString()方法，带示例

> 原文:[https://www . geesforgeks . org/abstract collection-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractcollection-tostring-method-in-java-with-examples/)

[JavaAbstractClass](https://www.geeksforgeeks.org/abstractcollection-in-java-with-examples/) 的 **toString()** 方法用于返回集合元素的字符串表示。

字符串表示包括集合中元素的列表表示，这些元素按照迭代器选取的顺序排列，用方括号[]括起来。此方法主要用于在字符串表示形式中显示字符串类型以外的集合(例如:对象、整数)。

**语法:**

```java
Object.toString();
```

**参数**该方法不取任何参数。

**返回**该方法返回集合的一个**字符串表示**。

以下示例说明了 toString()方法:

**例 1:**

```java
// Java program to demonstrate
// Abstract Collection toString() method

import java.util.*;

public class collection {
    public static void main(String args[])
    {
        // Creating an Empty AbstractCollection
        AbstractCollection<String> abs
            = new PriorityQueue<String>();

        // Use add() method
        // to add elements to the Collection
        abs.add("Welcome");
        abs.add("To");
        abs.add("Geeks");
        abs.add("For");
        abs.add("Geeks");

        // Using toString() method
        System.out.println(abs.toString());
    }
}
```

**输出:**

```java
[For, Geeks, To, Welcome, Geeks]

```

**例 2:**

```java
// Java program to demonstrate
// Abstract Collection toString() method

import java.util.*;

public class collection {
    public static void main(String args[])
    {
        // Creating an Empty AbstractCollection
        AbstractCollection<Integer> abs
            = new PriorityQueue<Integer>();

        // Use add() method
        // to add elements to the Collection
        abs.add(10);
        abs.add(20);
        abs.add(30);
        abs.add(40);

        // Using toString() method
        System.out.println(abs.toString());
    }
}
```

**输出:**

```java
[10, 20, 30, 40]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/abstractcollection . html # toString–](https://docs.oracle.com/javase/9/docs/api/java/util/AbstractCollection.html#toString--)