# Java 中的抽象集合 removeAll()方法，示例

> 原文:[https://www . geesforgeks . org/abstract collection-remove all-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractcollection-removeall-method-in-java-with-example/)

**Java . util . abstract Collection . remove all(Collection col)**方法用于从抽象集合中移除指定集合中存在的所有元素。

**语法:**

```java
AbstractCollection.removeAll(Collection col)
```

**参数:**该方法接受一个强制参数**列**，它是要从抽象集合中移除其元素的集合。

**返回值:**如果抽象集合由于操作而改变，该方法返回**真**，否则返回**假**。

**异常:**如果指定的集合为空，该方法将抛出**空指针异常**。

下面的程序说明了方法:

**程序 1:**

```java
// Java code to illustrate removeAll()
import java.util.*;

public class AbstractCollectionDemo {
    public static void main(String args[])
    {

        // Creating an empty AbstractCollection
        AbstractCollection<String> collection
            = new ArrayList<String>();

        // Use add() method to add
        // elements in the AbstractCollection
        collection.add("Geeks");
        collection.add("for");
        collection.add("Geeks");
        collection.add("10");
        collection.add("20");

        // Output the AbstractCollection
        System.out.println("AbstractCollection: "
                           + collection);

        // Creating an empty AbstractCollection
        AbstractCollection<String> colcollection
            = new ArrayList<String>();

        // Use add() method to add
        // elements in the AbstractCollection
        colcollection.add("Geeks");
        colcollection.add("for");
        colcollection.add("Geeks");

        // Remove the head using remove()
        boolean changed
            = collection.removeAll(colcollection);

        // Print the result
        if (changed)
            System.out.println("Collection removed");
        else
            System.out.println("Collection not removed");

        // Print the final AbstractCollection
        System.out.println("Final AbstractCollection: "
                           + collection);
    }
}
```

**Output:**

```java
AbstractCollection: [Geeks, for, Geeks, 10, 20]
Collection removed
Final AbstractCollection: [10, 20]

```

**程序 2:**

```java
// Java code to illustrate removeAll()
import java.util.*;

public class AbstractCollectionDemo {
    public static void main(String args[])
    {

        // Creating an empty AbstractCollection
        AbstractCollection<Integer> collection
            = new ArrayList<Integer>();

        // Use add() method to
        // add elements in the AbstractCollection
        collection.add(1);
        collection.add(2);
        collection.add(3);
        collection.add(10);
        collection.add(20);

        // Output the AbstractCollection
        System.out.println("AbstractCollection: "
                           + collection);

        // Creating an empty AbstractCollection
        AbstractCollection<Integer> colcollection
            = new ArrayList<Integer>();

        // Use add() method to add elements
        // in the AbstractCollection
        colcollection.add(30);
        colcollection.add(40);
        colcollection.add(50);

        // Remove the head using remove()
        boolean changed
            = collection.removeAll(colcollection);

        // Print the result
        if (changed)
            System.out.println("Collection removed");
        else
            System.out.println("Collection not removed");

        // Print the final AbstractCollection
        System.out.println("Final AbstractCollection: "
                           + collection);
    }
}
```

**Output:**

```java
AbstractCollection: [1, 2, 3, 10, 20]
Collection not removed
Final AbstractCollection: [1, 2, 3, 10, 20]

```