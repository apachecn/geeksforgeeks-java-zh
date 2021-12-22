# Java 中的抽象集合大小()方法，带示例

> 原文:[https://www . geesforgeks . org/abstract collection-size-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractcollection-size-method-in-java-with-examples/)

[**Java 抽象集合**](https://www.geeksforgeeks.org/abstractcollection-in-java-with-examples/) 的 **size()** 方法用于获取集合的大小或集合中存在的元素数量。
**语法:**

```
AbstractCollection.size()
```

**参数:**该方法不取任何参数。
**返回值:**该方法返回**大小**或集合中存在的元素数量。
以下程序说明了 AbstractCollection.size()方法的使用:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate size()

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

        // Displaying the size of the collection
        System.out.println("The size of the Collection is: "
                           + abs.size());
    }
}
```

**Output:** 

```
Collection: [4, Geeks, To, TreeSet, Welcome]
The size of the Collection is: 5
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate size()

import java.util.*;
import java.util.AbstractCollection;

public class AbstractCollectionDemo {
    public static void main(String args[])
    {

        // Creating an empty Collection
        AbstractCollection<String>
            abs = new LinkedList<String>();

        // Using add() method to add
        // elements in the Collection
        abs.add("Geeks");
        abs.add("for");
        abs.add("Geeks");
        abs.add("10");
        abs.add("20");

        // Displaying the Collection
        System.out.println("Collection:" + abs);

        // Displaying the size of the Collection
        System.out.println("The size of the Collection is: "
                           + abs.size());
    }
}
```

**Output:** 

```
Collection:[Geeks, for, Geeks, 10, 20]
The size of the Collection is: 5
```