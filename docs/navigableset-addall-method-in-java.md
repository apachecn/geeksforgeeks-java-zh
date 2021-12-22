# Java 中的 NavigableSet addAll()方法

> 原文:[https://www . geesforgeks . org/navigableset-addall-method-in-Java/](https://www.geeksforgeeks.org/navigableset-addall-method-in-java/)

**Java . util . NavigableSet . addall(Collection C)**方法用于将上述集合中的所有元素追加到现有的 navigatableset 中。元素是随机添加的，没有遵循任何特定的顺序。

**语法:**

```java
boolean addAll(Collection C)
```

**参数:**参数 *C* 是要添加到导航集中的任何类型的集合。

**返回值:**如果该方法成功地将集合 *C* 的元素追加到该导航集中，则该方法返回真，否则返回假。

**注**:Java 中 NavigableSet 接口的 addAll()方法是从 Set 接口继承而来的。

下面的程序说明了 Java . util . navigatableset . addall()方法:

**程序 1 :** 追加树导航集。

```java
// Java code to illustrate addAll()
import java.io.*;
import java.util.*;

public class TreeNavigableSetDemo {
    public static void main(String args[])
    {
        // Creating an empty NavigableSet
        NavigableSet<String> st1 = new TreeSet<String>();

        // Use add() method to add elements
        // into the NavigableSet
        st1.add("Welcome");
        st1.add("To");
        st1.add("Geeks");
        st1.add("4");
        st1.add("Geeks");
        st1.add("TreeNavigableSet");

        // Displaying the NavigableSet
        System.out.println("NavigableSet: " + st1);

        // Creating another NavigableSet
        NavigableSet<String> st2 = new TreeSet<String>();

        // Use add() method to add elements
        // into the NavigableSet
        st2.add("Hello");
        st2.add("World");

        // Using addAll() method to Append
        st1.addAll(st2);

        // Displaying the final NavigableSet
        System.out.println("NavigableSet: " + st1);
    }
}
```

**Output:**

```java
NavigableSet: [4, Geeks, To, TreeNavigableSet, Welcome]
NavigableSet: [4, Geeks, Hello, To, TreeNavigableSet, Welcome, World]

```

**程序 2 :** 追加数组列表。

```java
// Java code to illustrate addAll()
import java.io.*;
import java.util.*;

public class NavigableSetDemo {
    public static void main(String args[])
    {
        // Creating an empty NavigableSet
        NavigableSet<String> st1 = new TreeSet<String>();

        // Use add() method to add elements
        // into the NavigableSet
        st1.add("Welcome");
        st1.add("To");
        st1.add("Geeks");
        st1.add("4");
        st1.add("Geeks");
        st1.add("NavigableSet");

        // Displaying the NavigableSet
        System.out.println("Initial NavigableSet: " + st1);

        // An array collection is created
        ArrayList<String> collect = new ArrayList<String>();
        collect.add("A");
        collect.add("Computer");
        collect.add("Portal");

        // Using addAll() method to Append
        st1.addAll(collect);

        // Displaying the final NavigableSet
        System.out.println("Final NavigableSet: " + st1);
    }
}
```

**Output:**

```java
Initial NavigableSet: [4, Geeks, NavigableSet, To, Welcome]
Final NavigableSet: [4, A, Computer, Geeks, NavigableSet, Portal, To, Welcome]

```