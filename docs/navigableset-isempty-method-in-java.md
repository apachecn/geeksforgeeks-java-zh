# Java 中的 NavigableSet isEmpty()方法

> 原文:[https://www . geesforgeks . org/navigableset-isempty-method-in-Java/](https://www.geeksforgeeks.org/navigableset-isempty-method-in-java/)

Java . util . NavigableSet . isempty()方法用于检查 navigatableset 是否为空。如果导航集为空，则返回真，否则返回假。

**语法:**

```java
boolean isEmpty()
```

**参数:**该方法不取任何参数

**返回值:**如果导航集为空，则该方法返回真，否则返回假。

下面的程序说明了 Java . util . navigatableset . isempty()方法:

```java
// Java code to illustrate isEmpty()
import java.io.*;
import java.util.*;

public class NavigableSetDemo {
    public static void main(String args[])
    {
        // Creating an empty NavigableSet
        NavigableSet<String> st = new TreeSet<String>();

        // Use add() method to add elements into
        // the NavigableSet
        st.add("Welcome");
        st.add("To");
        st.add("Geeks");
        st.add("4");
        st.add("Geeks");

        // Displaying the NavigableSet
        System.out.println("NavigableSet: " + st);

        // Check for the empty NavigableSet
        System.out.println("Is the NavigableSet empty? "
                           + st.isEmpty());

        // Clearing the NavigableSet using clear() method
        st.clear();

        // Again Checking for the empty NavigableSet
        System.out.println("Is the NavigableSet empty? "
                           + st.isEmpty());
    }
}
```

**Output:**

```java
NavigableSet: [4, Geeks, To, Welcome]
Is the NavigableSet empty? false
Is the NavigableSet empty? true

```