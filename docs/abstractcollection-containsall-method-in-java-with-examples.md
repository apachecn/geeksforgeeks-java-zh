# 抽象集合包含 Java 中的 All()方法，示例

> 原文:[https://www . geesforgeks . org/abstract collection-contains all-in-Java-method-in-with-examples/](https://www.geeksforgeeks.org/abstractcollection-containsall-method-in-java-with-examples/)

**[Java 抽象集合](https://www.geeksforgeeks.org/abstractcollection-in-java-with-examples/)** 的 **containsAll()** 方法用于检查两个集合是否包含相同的元素。它将一个集合作为参数，如果该集合的所有元素都存在于另一个集合中，则返回 True。

**语法:**

```
AbstractCollection.containsAll(Collection C)
```

**参数:**参数 *C* 为集合。此参数指的是需要在此集合中检查其元素出现的集合。

**返回值:**如果此*集合*包含其他集合的所有元素，则该方法返回真，否则返回假。

下面的程序说明了 AbstractCollection.conatinsAll()方法:

**程序 1:**

```
// Java code to illustrate boolean containsAll()

import java.util.*;

class AbstractCollectionDemo {
    public static void main(String args[])
    {

        // Creating an empty Collection
        AbstractCollection<String>
            abs = new LinkedList<String>();

        // Use add() method to
        // add elements in the collection
        abs.add("Geeks");
        abs.add("for");
        abs.add("Geeks");
        abs.add("10");
        abs.add("20");

        // Creating another empty Collection
        AbstractCollection<String>
            abs2 = new LinkedList<String>();

        // Use add() method to
        // add elements in the collection
        abs2.add("Geeks");
        abs2.add("for");
        abs2.add("Geeks");
        abs2.add("10");
        abs2.add("20");

        // Check if the collection
        // contains same elements
        System.out.println("\nBoth the collections same: "
                           + abs.containsAll(abs2));
    }
}
```

**Output:**

```
Both the collections same: true

```

**程序 2:**

```
// Java code to illustrate boolean containsAll()

import java.util.*;

class AbstractCollectionDemo {
    public static void main(String args[])
    {

        // Creating an empty Collection
        AbstractCollection<String>
            abs = new LinkedList<String>();

        // Use add() method to
        // add elements in the collection
        abs.add("Geeks");
        abs.add("for");
        abs.add("Geeks");

        // Creating another empty Collection
        AbstractCollection<String>
            abs2 = new LinkedList<String>();

        // Use add() method to
        // add elements in the collection
        abs2.add("10");
        abs2.add("20");

        // Check if the collection
        // contains same elements
        System.out.println("\nBoth the collections same: "
                           + abs.containsAll(abs2));
    }
}
```

**Output:**

```
Both the collections same: false

```