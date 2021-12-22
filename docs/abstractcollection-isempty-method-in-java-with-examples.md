# 抽象集合是 Java 中的一个空()方法，带有示例

> 原文:[https://www . geesforgeks . org/abstract collection-isempty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractcollection-isempty-method-in-java-with-examples/)

**[Java 抽象集合](https://www.geeksforgeeks.org/abstractcollection-in-java-with-examples/)** 的 **isEmpty()** 方法用于检查和验证集合是否为空。如果集合为空，则返回真，否则返回假。

**语法:**

```
AbstractCollection.isEmpty()
```

**参数:**该方法不取任何参数。

**返回值:**如果集合为空，函数返回真，否则返回假。

下面的程序说明了 AbstractCollection.isEmpty()方法的使用:

**程序 1:**

```
// Java code to illustrate isEmpty() method

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
        abs.add("TreeSet");

        // Displaying the Collection
        System.out.println("Collection: " + abs);

        // Check for the empty collection
        System.out.println("Is the collection empty? "
                           + abs.isEmpty());

        // Clearing the collection
        // using clear() method
        abs.clear();

        // Again Checking for the empty collection
        System.out.println("Is the collection empty? "
                           + abs.isEmpty());
    }
}
```

**Output:**

```
Collection: [4, Geeks, To, TreeSet, Welcome]
Is the collection empty? false
Is the collection empty? true

```

**程序 2:**

```
// Java code to illustrate isEmpty() method

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
        abs.add("ArrayList");

        // Displaying the Collection
        System.out.println("Collection: " + abs);

        // Check for the empty collection
        System.out.println("Is the collection empty? "
                           + abs.isEmpty());

        // Clearing the collection using clear() method
        abs.clear();

        // Again Checking for the empty collection
        System.out.println("Is the collection empty? "
                           + abs.isEmpty());
    }
}
```

**Output:**

```
Collection: [Welcome, To, Geeks, 4, Geeks, ArrayList]
Is the collection empty? false
Is the collection empty? true

```