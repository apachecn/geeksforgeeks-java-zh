# 抽象集合移除()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/abstract collection-remove-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractcollection-remove-method-in-java-with-examples/)

**[Java 抽象集合](https://www.geeksforgeeks.org/abstractcollection-in-java-with-examples/)** 的**移除(对象 O)** 方法是从集合中移除特定元素。

**语法:**

```java
AbstractCollection.remove(Object O)
```

**参数:**参数 *O* 属于集合类型，指定要从集合中移除的元素。

**返回值:**如果参数中指定的元素最初出现在集合中并被成功移除，则该方法返回*真*，否则返回*假*。

下面的程序说明了 Java . util . abstract collection . remove()方法:

**程序 1** :

```java
// Java code to illustrate remove()

import java.util.*;
import java.util.AbstractCollection;

public class AbstractCollectionDemo {
    public static void main(String args[])
    {

        // Creating an empty AbstractCollection
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

        // Removing elements using remove() method
        abs.remove("Geeks");
        abs.remove("4");
        abs.remove("TreeSet");

        // Displaying the Collection after removal
        System.out.println("New Collection: " + abs);
    }
}
```

**Output:**

```java
Collection: [4, Geeks, To, TreeSet, Welcome]
New Collection: [To, Welcome]

```

**程序 2:**

```java
// Java code to illustrate remove()

import java.util.*;
import java.util.AbstractCollection;

public class AbstractCollectionDemo {
    public static void main(String args[])
    {

        // Creating an empty AbstractCollection
        AbstractCollection<String>
            abs = new LinkedList<String>();

        // Use add() method to add
        // elements into the Collection
        abs.add("Welcome");
        abs.add("To");
        abs.add("Geeks");
        abs.add("4");
        abs.add("Geeks");
        abs.add("LinkedList");

        // Displaying the Collection
        System.out.println("Collection: " + abs);

        // Removing elements using remove() method
        abs.remove("Geeks");
        abs.remove("4");
        abs.remove("LinkedList");

        // Displaying the Collection after removal
        System.out.println("New Collection: " + abs);
    }
}
```

**Output:**

```java
Collection: [Welcome, To, Geeks, 4, Geeks, LinkedList]
New Collection: [Welcome, To, Geeks]

```