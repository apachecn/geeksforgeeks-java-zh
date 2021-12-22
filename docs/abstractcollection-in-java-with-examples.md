# Java 抽象集合，带示例

> 原文:[https://www . geesforgeks . org/abstract collection-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractcollection-in-java-with-examples/)

Java 中的**抽象集合**类是 [Java 集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的一部分，实现了*集合接口*。它用于实现一个不可修改的集合，对于这个集合，只需要扩展这个抽象集合类，并且只实现迭代器和大小方法。

**等级等级:**

```java
java.lang.Object
 ↳ java.util
    ↳ Class AbstractCollection<E>

```

**语法:**

```java
public abstract class AbstractCollection<E>
    extends Object
       implements Collection<E>

where E is the type of elements maintained
by this collection.

```

**Java 抽象集合中的构造函数:**

*   **protected AbstractCollection()**:默认的构造函数，但是受到保护，不允许创建 abstract collection 对象。

下面是用 Java 举例说明 AbstractCollection 的示例程序:

```java
// Java code to illustrate AbstractCollection

import java.util.*;
import java.util.AbstractCollection;

public class GFG {
    public static void main(String[] args)
    {
        // Create an empty collection
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
    }
}
```

**输出:**

```java
AbstractCollection: [Welcome, To, Geeks, 4, Geeks]

```

**Java 抽象集合中的方法:**

1.  **[Add (e e)](https://www.geeksforgeeks.org/abstractcollection-add-method-in-java-with-examples/) :** This method ensures that this collection contains the specified elements (optional operation).
2.  **[Add all (set C)](https://www.geeksforgeeks.org/abstractcollection-addall-method-in-java-with-examples/) :** This method adds all elements in the specified set to this set (optional operation).
3.  **[clear ()](https://www.geeksforgeeks.org/abstractcollection-clear-method-in-java-with-examples/) :** This method removes all elements from this set (optional operation).
4.  **[contains (objecto)](https://www.geeksforgeeks.org/abstractcollection-contains-method-in-java-with-examples/) :** This method returns true if this collection contains the specified element.
5.  **[contains all (collection c)](https://www.geeksforgeeks.org/abstractcollection-containsall-method-in-java-with-examples/) :** This method returns true if this collection contains all the elements in the specified collection.
6.  **[isempty ()](https://www.geeksforgeeks.org/abstractcollection-isempty-method-in-java-with-examples/) :** This method returns true if this collection contains no elements.
7.  **[Iterator ()](https://www.geeksforgeeks.org/absractcollection-iterator-method-in-java-with-examples/) :** This method returns the iterator of the elements contained in this collection.
8.  **[Remove (object o)](https://www.geeksforgeeks.org/abstractcollection-remove-method-in-java-with-examples/) :** This method removes the single instance of the specified element (if it exists) from the collection (optional operation).
9.  **[size ()](https://www.geeksforgeeks.org/abstractcollection-size-method-in-java-with-examples/) :** This method returns the number of elements in this collection.
10.  **[toarray ()](https://www.geeksforgeeks.org/abstractcollection-toarray-method-in-java-with-examples/) :** This method returns an array containing all the elements in this collection.
11.  **[toarray (t [] a)](https://www.geeksforgeeks.org/abstractcollection-toarray-method-in-java-with-examples/) :** This method returns an array containing all the elements in this collection; The runtime type of the returned array is the runtime type of the specified array.
12.  **tostring ():** This method returns the string representation of this collection.

**例:**

```java
// Java code to illustrate
// methods of AbstractCollection

import java.util.*;
import java.util.AbstractCollection;

public class AbstractCollectionDemo {
    public static void main(String args[])
    {

        // Creating an empty collection
        AbstractCollection<String>
            abs1 = new TreeSet<String>();

        // Use add() method to add
        // elements into the Collection
        abs1.add("Welcome");
        abs1.add("To");
        abs1.add("Geeks");
        abs1.add("4");
        abs1.add("Geeks");
        abs1.add("TreeSet");

        // Displaying the Collection
        System.out.println("AbstractCollection 1: "
                           + abs1);

        // Creating anothe Collection
        AbstractCollection<String>
            abs2 = new TreeSet<String>();

        // Displaying the Collection
        System.out.println("AbstractCollection 2: "
                           + abs2);

        // Using addAll() method to Append
        abs2.addAll(abs1);

        // Displaying the Collection
        System.out.println("AbstractCollection 2: "
                           + abs2);

        // Clearing the collection
        // using clear() method
        abs1.clear();

        // Check for the empty collection
        System.out.println("Is the collection empty? "
                           + abs1.isEmpty());
    }
}
```

**输出:**

```java
AbstractCollection 1: [4, Geeks, To, TreeSet, Welcome]
AbstractCollection 2: []
AbstractCollection 2: [4, Geeks, To, TreeSet, Welcome]
Is the collection empty? true

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/abstract collection . html](https://docs.oracle.com/javase/7/docs/api/java/util/AbstractCollection.html)