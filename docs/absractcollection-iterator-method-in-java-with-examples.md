# Java 中的抽象集合迭代器()方法，带示例

> 原文:[https://www . geesforgeks . org/abstractcollection-iterator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/absractcollection-iterator-method-in-java-with-examples/)

**[Java 抽象集合](https://www.geeksforgeeks.org/abstractcollection-in-java-with-examples/)** 的**迭代器()**方法用于返回一个与集合元素相同的迭代器。元素从集合中随机返回。

**语法:**

```java
Iterator iterate_value = AbstractCollection.iterator();
```

**参数:**函数不取任何参数。

**返回值:**方法迭代集合的元素并返回值(迭代器)。

下面的程序说明了 AbstractCollection.iterator()方法的使用:

**程序 1:**

```java
// Java code to illustrate iterator()

import java.util.*;
import java.util.AbstractCollection;

public class AbstractCollectionDemo {
    public static void main(String args[])
    {

        // Creating an empty Collection
        AbstractCollection<String>
            abs = new TreeSet<String>();

        // Use add() method to add
        // elements into the Collection
        abs.add("Welcome");
        abs.add("To");
        abs.add("Geeks");
        abs.add("4");
        abs.add("Geeks");

        // Displaying the Collection
        System.out.println("Collection: " + abs);

        // Creating an iterator
        Iterator value = abs.iterator();

        // Displaying the values
        // after iterating through the collection
        System.out.println("The iterator values are: ");

        while (value.hasNext()) {

            System.out.println(value.next());
        }
    }
}
```

**Output:**

```java
Collection: [4, Geeks, To, Welcome]
The iterator values are: 
4
Geeks
To
Welcome

```

**程序 2:**

```java
// Java code to illustrate iterator()

import java.util.*;
import java.util.AbstractCollection;

public class AbstractCollectionDemo {
    public static void main(String args[])
    {

        // Creating an empty Collection
        AbstractCollection<String>
            abs = new ArrayList<String>();

        // Use add() method to add
        // elements into the Collection
        abs.add("Welcome");
        abs.add("To");
        abs.add("Geeks");
        abs.add("4");
        abs.add("Geeks");

        // Displaying the Collection
        System.out.println("Collection: " + abs);

        // Creating an iterator
        Iterator value = abs.iterator();

        // Displaying the values
        // after iterating through the collection
        System.out.println("The iterator values are: ");

        while (value.hasNext()) {

            System.out.println(value.next());
        }
    }
}
```

**Output:**

```java
Collection: [Welcome, To, Geeks, 4, Geeks]
The iterator values are: 
Welcome
To
Geeks
4
Geeks

```