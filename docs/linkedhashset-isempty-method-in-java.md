# Java 中的 LinkedHashSet isEmpty()方法

> 原文:[https://www . geeksforgeeks . org/link edhashset-isempty-method-in-Java/](https://www.geeksforgeeks.org/linkedhashset-isempty-method-in-java/)

Java . util . LinkedHashSet . isempty()方法用于检查 LinkedHashSet 是否为空。如果链接哈希集为空，则返回真，否则返回假。

**语法:**

```java
Linked_Hash_Set.isEmpty()
```

**参数:**该方法不取任何参数

**返回值:**如果集合为空，函数返回真，否则返回假。

下面程序举例说明了 Java . util . linkedhashset . isempty()方法:

## Java

```java
// Java code to illustrate isEmpty()
import java.io.*;
import java.util.LinkedHashSet;

public class LinkedHashSetDemo {
    public static void main(String args[])
    {
        // Creating an empty LinkedHashSet
        LinkedHashSet<String> set = new LinkedHashSet<String>();

        // Use add() method to add elements into the Set
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("4");
        set.add("Geeks");

        // Displaying the LinkedHashSet
        System.out.println("LinkedHashSet: " + set);

        // Check for the empty set
        System.out.println("Is the set empty: " + set.isEmpty());

        // Clearing the set using clear() method
        set.clear();

        // Again Checking for the empty set
        System.out.println("Is the set empty: " + set.isEmpty());
    }
}
```

**输出:**

```java
LinkedHashSet: [Welcome, To, Geeks, 4]
Is the set empty: false
Is the set empty: true
```