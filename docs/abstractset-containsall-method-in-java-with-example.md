# 抽象集包含 Java 中的 All()方法，示例

> 原文:[https://www . geesforgeks . org/abstract set-contains all-in-Java-method-with-example/](https://www.geeksforgeeks.org/abstractset-containsall-method-in-java-with-example/)

**Java 抽象集**的 **containsAll()** 方法用于检查两个集合是否包含相同的元素。它将一个集合作为参数，如果该集合的所有元素都存在于另一个集合中，则返回 True。

**语法:**

```java
public boolean containsAll(Collection C)
```

**参数:**参数 *C* 为集合。该参数是指需要在该集合中检查其元素出现的集合。

**返回值:**如果这个*集合*包含其他集合的所有元素，方法返回真，否则返回假。

下面的程序说明了 AbstractSet.conatinsAll()方法:

**程序 1:**

```java
// Java code to illustrate
// AbstractSet containsAll()

import java.util.*;

class AbstractSetDemo {
    public static void main(String args[])
    {

        // Creating an empty set
        AbstractSet<String>
            abs = new TreeSet<String>();

        // Use add() method to
        // add elements in the set
        abs.add("Geeks");
        abs.add("for");
        abs.add("Geeks");
        abs.add("10");
        abs.add("20");

        // prints the set
        System.out.println("AbstractSet 1: "
                           + abs);

        // Creating another empty set
        AbstractSet<String>
            abs2 = new TreeSet<String>();

        // Use add() method to
        // add elements in the set
        abs2.add("Geeks");
        abs2.add("for");
        abs2.add("Geeks");
        abs2.add("10");
        abs2.add("20");

        // prints the set
        System.out.println("AbstractSet 2: "
                           + abs2);

        // Check if the set
        // contains same elements
        System.out.println("\nDoes set 1 contains set 2: "
                           + abs.containsAll(abs2));
    }
}
```

**Output:**

```java
AbstractSet 1: [10, 20, Geeks, for]
AbstractSet 2: [10, 20, Geeks, for]

Does set 1 contains set 2: true

```

**程序 2:**

```java
// Java code to illustrate boolean containsAll()

import java.util.*;

class AbstractSetDemo {
    public static void main(String args[])
    {

        // Creating an empty set
        AbstractSet<String>
            abs = new TreeSet<String>();

        // Use add() method to
        // add elements in the set
        abs.add("Geeks");
        abs.add("for");
        abs.add("Geeks");

        // prints the set
        System.out.println("AbstractSet 1: "
                           + abs);

        // Creating another empty set
        AbstractSet<String>
            abs2 = new TreeSet<String>();

        // Use add() method to
        // add elements in the set
        abs2.add("10");
        abs2.add("20");

        // prints the set
        System.out.println("AbstractSet 2: "
                           + abs2);

        // Check if the set
        // contains same elements
        System.out.println("\nDoes set 1 contains set 2: "
                           + abs.containsAll(abs2));
    }
}
```

**Output:**

```java
AbstractSet 1: [Geeks, for]
AbstractSet 2: [10, 20]

Does set 1 contains set 2: false

```