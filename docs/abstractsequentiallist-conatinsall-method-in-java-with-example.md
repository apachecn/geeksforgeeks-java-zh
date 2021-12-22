# Java 中的抽象顺序列表 conatinsAll()方法，示例

> 原文:[https://www . geeksforgeeks . org/abstractsequentialist-conatinsall-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractsequentiallist-conatinsall-method-in-java-with-example/)

**Java 抽象顺序列表**的 **containsAll()** 方法用于检查两个集合是否包含相同的元素。它将一个集合作为参数，如果该集合的所有元素都存在于另一个集合中，则返回 True。

**语法:**

```
public boolean containsAll(Collection C)
```

**参数:**参数 *C* 为集合。此参数指的是需要在此集合中检查其元素出现的集合。

**返回值:**如果此*集合*包含其他集合的所有元素，则该方法返回真，否则返回假。

下面的程序说明了 abstractsequentialist . conatinsall()方法:

**程序 1:**

```
// Java code to illustrate
// AbstractSequentialList containsAll()

import java.util.*;

class AbstractSequentialListDemo {
    public static void main(String args[])
    {

        // Creating an empty Collection
        AbstractSequentialList<String>
            abs = new LinkedList<String>();

        // Use add() method to
        // add elements in the collection
        abs.add("Geeks");
        abs.add("for");
        abs.add("Geeks");
        abs.add("10");
        abs.add("20");

        // prints the list
        System.out.println("AbstractSequentialList 1: "
                           + abs);

        // Creating another empty Collection
        AbstractSequentialList<String>
            abs2 = new LinkedList<String>();

        // Use add() method to
        // add elements in the collection
        abs2.add("Geeks");
        abs2.add("for");
        abs2.add("Geeks");
        abs2.add("10");
        abs2.add("20");

        // prints the list
        System.out.println("AbstractSequentialList 2: "
                           + abs2);

        // Check if the collection
        // contains same elements
        System.out.println("\nBoth the collections same: "
                           + abs.containsAll(abs2));
    }
}
```

**Output:**

```
AbstractSequentialList 1: [Geeks, for, Geeks, 10, 20]
AbstractSequentialList 2: [Geeks, for, Geeks, 10, 20]

Both the collections same: true

```

**程序 2:**

```
// Java code to illustrate boolean containsAll()

import java.util.*;

class AbstractSequentialListDemo {
    public static void main(String args[])
    {

        // Creating an empty Collection
        AbstractSequentialList<String>
            abs = new LinkedList<String>();

        // Use add() method to
        // add elements in the collection
        abs.add("Geeks");
        abs.add("for");
        abs.add("Geeks");

        // prints the list
        System.out.println("AbstractSequentialList 1: "
                           + abs);

        // Creating another empty Collection
        AbstractSequentialList<String>
            abs2 = new LinkedList<String>();

        // Use add() method to
        // add elements in the collection
        abs2.add("10");
        abs2.add("20");

        // prints the list
        System.out.println("AbstractSequentialList 2: "
                           + abs2);

        // Check if the collection
        // contains same elements
        System.out.println("\nAre both collections same: "
                           + abs.containsAll(abs2));
    }
}
```

**Output:**

```
AbstractSequentialList 1: [Geeks, for, Geeks]
AbstractSequentialList 2: [10, 20]

Are both collections same: false

```