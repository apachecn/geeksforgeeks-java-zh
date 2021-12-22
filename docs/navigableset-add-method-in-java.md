# Java 中的 NavigableSet add()方法

> 原文:[https://www . geesforgeks . org/navigableset-add-method-in-Java/](https://www.geeksforgeeks.org/navigableset-add-method-in-java/)

Java 中 navigatableset 的 add()方法用于将特定元素添加到 navigatableset 集合中。只有当指定的元素尚未出现在导航集中时，函数才会添加该元素，否则，如果该元素已出现在导航集中，函数将返回 False。

**语法:**

```
boolean add(E element)

Where, E is the type of element maintained
by this NavigableSet collection.

```

**参数:**参数*元素*属于该导航集维护的元素类型，是指要添加到导航集中的元素。

**返回值:**如果元素不在导航集中并且是新的，函数返回真，否则如果元素已经在导航集中，函数返回假。

**注意:**Java 中 NavigableSet 接口的 add()方法是从 Set 接口继承而来的。

下面的程序说明了 Java . util . navigatableset . add()方法的使用:

**程序 1** :

```
// Java code to illustrate add() method
import java.io.*;
import java.util.*;

public class NavigableSetDemo {
    public static void main(String args[])
    {
        // Creating an empty NavigableSet
        NavigableSet<String> s = new TreeSet<String>();

        // Use add() method to add elements into
        // the NavigableSet
        s.add("Welcome");
        s.add("To");
        s.add("Geeks");
        s.add("4");
        s.add("Geeks");
        s.add("NavigableSet");

        // Displaying the NavigableSet
        System.out.println("NavigableSet: " + s);
    }
}
```

**输出:**

```
NavigableSet: [4, Geeks, NavigableSet, To, Welcome]

```

**程序二** :

```
// Java code to illustrate add() method
import java.io.*;
import java.util.*;

public class NavigableSetDemo {
    public static void main(String args[])
    {
        // Creating an empty NavigableSet
        NavigableSet<Integer> s = new TreeSet<Integer>();

        // Use add() method to add elements into the NavigableSet
        s.add(10);
        s.add(20);
        s.add(30);
        s.add(40);
        s.add(50);
        s.add(60);

        // Displaying the NavigableSet
        System.out.println("NavigableSet: " + s);
    }
}
```

**输出:**

```
NavigableSet: [10, 20, 30, 40, 50, 60]

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/navigatableset . html # add(E)](https://docs.oracle.com/javase/7/docs/api/java/util/NavigableSet.html#add(E))