# 抽象集合用示例清除 Java 中的()方法

> 原文:[https://www . geesforgeks . org/abstract collection-clear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractcollection-clear-method-in-java-with-examples/)

Java 中 **[Java 抽象集合](https://www.geeksforgeeks.org/abstractcollection-in-java-with-examples/)** 的 **clear()** 方法用于从集合中移除所有元素。使用 clear()方法只会清除集合中的所有元素，而不会删除集合。换句话说，可以说 clear()方法仅用于清空现有的抽象集合。

**语法:**

```
AbstractCollection.clear()
```

**返回值:**函数不返回值。

下面的程序说明了 AbstractCollection.clear()方法:

**程序 1:**

```
// Java code to illustrate clear(Object o)
// of AbstractCollelction

import java.util.*;
import java.util.AbstractCollection;

public class AbstractCollectionDemo {
    public static void main(String[] args)
    {

        // Create an empty Collection
        AbstractCollection<Object>
            abs = new ArrayList<Object>();

        // Use add() method to add
        // elements in the collection
        abs.add("Welcome");
        abs.add("To");
        abs.add("Geeks");
        abs.add("4");
        abs.add("Geeks");

        // Displaying the Collection
        System.out.println("AbstractCollection: "
                           + abs);

        // Clearing the Collection
        abs.clear();

        // Displaying the Collection
        System.out.println("AbstractCollection "
                           + "after using clear: "
                           + abs);
    }
}
```

**Output:**

```
AbstractCollection: [Welcome, To, Geeks, 4, Geeks]
AbstractCollection after using clear: []

```

**程序 2:**

```
// Java code to illustrate clear(Object o)
// of AbstractCollelction

import java.util.*;
import java.util.AbstractCollection;

public class AbstractCollectionDemo {
    public static void main(String[] args)
    {

        // Create an empty collection
        AbstractCollection<Object>
            abs = new LinkedList<Object>();

        // Use add() method to add
        // elements in the collection
        abs.add(15);
        abs.add(20);
        abs.add(25);
        abs.add(30);
        abs.add(35);

        // Displaying the Collection
        System.out.println("AbstractCollection: "
                           + abs);

        // Clearing the Collection
        abs.clear();

        // Displaying the Collection
        System.out.println("AbstractCollection "
                           + "after using clear: "
                           + abs);
    }
}
```

**Output:**

```
AbstractCollection: [15, 20, 25, 30, 35]
AbstractCollection after using clear: []

```