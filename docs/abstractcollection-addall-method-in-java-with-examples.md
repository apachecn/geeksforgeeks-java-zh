# Java 中的抽象集合 addAll()方法，带示例

> 原文:[https://www . geesforgeks . org/abstract collection-addall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractcollection-addall-method-in-java-with-examples/)

**[Java 抽象集合](https://www.geeksforgeeks.org/abstractcollection-in-java-with-examples/)** 的 **addAll( *集合 C* )** 方法用于将所述集合中的所有元素追加到*这个*集合中。元素是随机添加的，没有任何特定的顺序。

**语法:**

```java
boolean addAll(*Collection C)*
```

**参数:**参数 *C* 是要添加到集合中的任何类型的集合。

**返回值:**如果该方法成功地将集合 *C* 的元素追加到现有集合中，则该方法返回真，否则返回假。

下面的程序说明了 AbstractCollection.addAll()方法:

**程序 1:**

```java
// Java code to illustrate addAll()
// method of AbstractCollection

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
    }
}
```

**Output:**

```java
AbstractCollection 1: [4, Geeks, To, TreeSet, Welcome]
AbstractCollection 2: []
AbstractCollection 2: [4, Geeks, To, TreeSet, Welcome]

```

**程序 2:**

```java
// Java code to illustrate addAll()
// method of AbstractCollection

import java.util.*;
import java.util.AbstractCollection;

public class AbstractCollectionDemo {
    public static void main(String args[])
    {

        // Creating an empty collection
        AbstractCollection<Integer>
            abs1 = new TreeSet<Integer>();

        // Use add() method to add
        // elements into the Collection
        abs1.add(10);
        abs1.add(20);
        abs1.add(30);
        abs1.add(40);
        abs1.add(50);

        // Displaying the Collection
        System.out.println("AbstractCollection 1: "
                           + abs1);

        // Creating anothe Collection
        AbstractCollection<Integer>
            abs2 = new TreeSet<Integer>();

        // Displaying the Collection
        System.out.println("AbstractCollection 2: "
                           + abs2);

        // Using addAll() method to Append
        abs2.addAll(abs1);

        // Displaying the Collection
        System.out.println("AbstractCollection 2: "
                           + abs2);
    }
}
```

**Output:**

```java
AbstractCollection 1: [10, 20, 30, 40, 50]
AbstractCollection 2: []
AbstractCollection 2: [10, 20, 30, 40, 50]

```