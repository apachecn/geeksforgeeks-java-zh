# Java 中 LinkedHashSet size()方法

> 原文:[https://www . geeksforgeeks . org/link edhashset-size-method-in-Java/](https://www.geeksforgeeks.org/linkedhashset-size-method-in-java/)

Java.util.LinkedHashSet.size()方法用于获取 LinkedHashSet 的大小或 LinkedHashSet 中存在的元素数量。

**语法:**

```java
Linked_Hash_Set.size()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回 LinkedHashSet 中存在的元素的大小或数量。

下面程序举例说明了 Java.util.LinkedHashSet.size()方法:

```java
// Java code to illustrate LinkedHashSet.size() method
import java.util.*;
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

        // Displaying the size of the LinkedHashSet
        System.out.println("The size of the set is: "
                           + set.size());
    }
}
```

T3】输出:

```java
LinkedHashSet: [Welcome, To, Geeks, 4]
The size of the set is: 4

```