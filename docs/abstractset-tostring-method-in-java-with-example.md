# 用示例

在 Java 中抽象设置 toString()方法

> 原文:[https://www . geesforgeks . org/abstract set-tostring-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractset-tostring-method-in-java-with-example/)

**Java 抽象集**的 **toString()** 方法用于返回集合元素的字符串表示。

字符串表示包括集合元素的集合表示，其顺序由方括号[]中的迭代器选取。此方法主要用于在字符串表示形式中显示字符串类型以外的集合(例如:对象、整数)。

**语法:**

```java
public String toString()
```

**参数**该方法不取任何参数。

**返回**该方法返回集合的**字符串表示**。

以下示例说明了 toString()方法:

**例 1:**

```java
// Java program to demonstrate
// Abstract Collection toString() method

import java.util.*;

public class collection {
    public static void main(String args[])
    {
        // Creating an Empty AbstractSet
        AbstractSet<String> abs
            = new TreeSet<String>();

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

**Output:**

```java
[For, Geeks, To, Welcome]

```

**例 2:**

```java
// Java program to demonstrate
// Abstract Collection toString() method

import java.util.*;

public class collection {
    public static void main(String args[])
    {
        // Creating an Empty AbstractSet
        AbstractSet<Integer> abs
            = new TreeSet<Integer>();

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

**Output:**

```java
[10, 20, 30, 40]

```