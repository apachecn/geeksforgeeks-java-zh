# 抽象集包含 Java 中的()方法，示例

> 原文:[https://www . geesforgeks . org/abstract set-contains-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractset-contains-method-in-java-with-example/)

**Java 抽象集**的 **contains()** 方法用于检查集合中是否存在元素。它将元素作为参数，如果元素存在于集合中，则返回 True。

**语法:**

```java
public boolean contains(Object element)
```

**参数:**参数*元素*为设定类型。该参数是指需要在集合中检查其出现的元素。

**返回值:**该方法返回一个**布尔值**。如果元素存在于集合中，则返回真，否则返回假。

下面的程序说明了 AbstractSet.contains()方法:

**程序 1:**

```java
// Java code to illustrate
// AbstractSet.contains()

import java.util.*;

public class GFG {
    public static void main(String args[])
    {

        // Creating an empty set
        AbstractSet<String>
            abs = new TreeSet<String>();

        // Use add() method to add
        // elements in the set
        abs.add("Geeks");
        abs.add("for");
        abs.add("Geeks");
        abs.add("10");
        abs.add("20");

        // Displaying the set
        System.out.println("AbstractSet: "
                           + abs);

        // Check if the set contains "Hello"
        System.out.println("\nDoes the set"
                           + " contains 'Hello': "
                           + abs.contains("Hello"));

        // Check if the set contains "20"
        System.out.println("Does the set"
                           + " contains '20': "
                           + abs.contains("20"));

        // Check if the set contains "Geeks"
        System.out.println("Does the set"
                           + " contains 'Geeks': "
                           + abs.contains("Geeks"));
    }
}
```

**Output:**

```java
AbstractSet: [10, 20, Geeks, for]

Does the set contains 'Hello': false
Does the set contains '20': true
Does the set contains 'Geeks': true

```

**程序 2:**

```java
// Java code to illustrate
// AbstractSet.contains()

import java.util.*;

public class GFG {
    public static void main(String args[])
    {

        // Creating an empty set
        AbstractSet<Integer>
            abs = new TreeSet<Integer>();

        // Use add() method to add
        // elements in the set
        abs.add(10);
        abs.add(20);
        abs.add(30);
        abs.add(40);
        abs.add(50);

        // Displaying the set
        System.out.println("AbstractSet:"
                           + abs);

        // Check if the set contains 10
        System.out.println("\nDoes the set "
                           + "contains '10': "
                           + abs.contains(10));

        // Check if the set contains 50
        System.out.println("\nDoes the set"
                           + " contains '50': "
                           + abs.contains(50));

        // Check if the set contains 100
        System.out.println("Does the set"
                           + " contains '100': "
                           + abs.contains(100));
    }
}
```

**Output:**

```java
AbstractSet:[10, 20, 30, 40, 50]

Does the set contains '10': true

Does the set contains '50': true
Does the set contains '100': false

```