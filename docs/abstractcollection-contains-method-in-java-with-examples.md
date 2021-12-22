# 抽象集合包含 Java 中的()方法，示例

> 原文:[https://www . geesforgeks . org/abstract collection-contains-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractcollection-contains-method-in-java-with-examples/)

[**Java 抽象集合**](https://www.geeksforgeeks.org/abstractcollection-in-java-with-examples/) 的 **contains()** 方法用于检查集合中是否存在元素。它将元素作为参数，如果集合中存在该元素，则返回 True。
**语法:**

```
AbstractCollection.contains(Object element)
```

**参数:**参数*元素*为集合类型。此参数引用需要在集合中检查其出现的元素。
**返回值:**如果集合中存在*元素*，则该方法返回真，否则返回假。
下面的程序说明了 Java . util . abstract collection . contains()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate boolean contains()

import java.util.*;
import java.util.AbstractCollection;

public class AbstractCollectionDemo {
    public static void main(String args[])
    {

        // Creating an empty Collection
        AbstractCollection<String>
            abs = new LinkedList<String>();

        // Use add() method to add
        // elements in the collection
        abs.add("Geeks");
        abs.add("for");
        abs.add("Geeks");
        abs.add("10");
        abs.add("20");

        // Displaying the collection
        System.out.println("Abstract Collection:"
                           + abs);

        // Check if the collection contains "Hello"
        System.out.println("\nDoes the Collection"
                           + " contains 'Hello': "
                           + abs.contains("Hello"));

        // Check if the Collection contains "20"
        System.out.println("Does the collection"
                           + " contains '20': "
                           + abs.contains("20"));

        // Check if the Collection contains "Geeks"
        System.out.println("Does the Collection"
                           + " contains 'Geeks': "
                           + abs.contains("Geeks"));
    }
}
```

**Output:** 

```
Abstract Collection:[Geeks, for, Geeks, 10, 20]

Does the Collection contains 'Hello': false
Does the collection contains '20': true
Does the Collection contains 'Geeks': true
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate boolean contains()

import java.util.*;
import java.util.AbstractCollection;

public class AbstractCollectionDemo {
    public static void main(String args[])
    {

        // Creating an empty Collection
        AbstractCollection<String>
            abs = new TreeSet<String>();

        // Use add() method to add
        // elements in the collection
        abs.add("Geeks");
        abs.add("for");
        abs.add("Geeks");
        abs.add("TreeSet");
        abs.add("20");

        // Displaying the collection
        System.out.println("Abstract Collection:"
                           + abs);

        // Check if the collection contains "TreeSet"
        System.out.println("\nDoes the Collection "
                           + "contains 'TreeSet': "
                           + abs.contains("TreeSet"));

        // Check if the collection contains "Hello"
        System.out.println("\nDoes the Collection"
                           + " contains 'Hello': "
                           + abs.contains("Hello"));

        // Check if the Collection contains "20"
        System.out.println("Does the collection"
                           + " contains '20': "
                           + abs.contains("20"));

        // Check if the Collection contains "Geeks"
        System.out.println("Does the Collection"
                           + " contains 'Geeks': "
                           + abs.contains("Geeks"));
    }
}
```

**Output:** 

```
Abstract Collection:[20, Geeks, TreeSet, for]

Does the Collection contains 'TreeSet': true

Does the Collection contains 'Hello': false
Does the collection contains '20': true
Does the Collection contains 'Geeks': true
```