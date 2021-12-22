# Java 中的 NavigableSet clear()方法

> 原文:[https://www . geesforgeks . org/navigableset-clear-method-in-Java/](https://www.geeksforgeeks.org/navigableset-clear-method-in-java/)

Java . util . NavigableSet . clear()方法用于从 navigatableset 中移除所有元素。使用 clear()方法只会清除导航集中的所有元素，而不会删除导航集。换句话说，我们可以说 clear()方法仅用于清空现有的 NavigableSet。

**语法:**

```java
void clear()
```

**参数:**该方法不取任何参数

**返回值:**该方法不返回值。

下面程序举例说明了 Java.util.method.clear()方法:

```java
// Java code to illustrate clear()
import java.io.*;
import java.util.*;

public class NavigableSetDemo {
    public static void main(String args[])
    {
        // Creating an empty NavigableSet
        NavigableSet<String> st = new TreeSet<String>();

        // Use add() method to add elements into the NavigableSet
        st.add("Welcome");
        st.add("To");
        st.add("Geeks");
        st.add("4");
        st.add("Geeks");

        // Displaying the NavigableSet
        System.out.println("Initial NavigableSet: " + st);

        // Clearing the NavigableSet using clear() method
        st.clear();

        // Displaying the final NavigableSet after clearing;
        System.out.println("The final NavigableSet: " + st);
    }
}
```

**输出:**

```java
Initial NavigableSet: [4, Geeks, To, Welcome]
The final NavigableSet: []

```