# Java 中 LinkedHashSet remove()方法

> 原文:[https://www . geeksforgeeks . org/link edhashset-remove-method-in-Java/](https://www.geeksforgeeks.org/linkedhashset-remove-method-in-java/)

Java . util . LinkedHashSet . remove(Object O)方法用于从 LinkedHashSet 中移除特定元素。

**语法:**

```java
LinkedHashSet.remove(Object O)
```

**参数:**参数 *O* 属于链接哈希集类型，指定要从链接哈希集中删除的元素。

**返回值:**如果指定的元素存在于 LinkedHashSet 中，该方法返回 True，否则返回 False。

下面程序举例说明了【对象 O】方法:

```java
// Java code to illustrate LinkedHashSet.remove() method
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

        // Removing elements using remove() method
        set.remove("Geeks");
        set.remove("4");
        set.remove("Welcome");

        // Displaying the LinkedHashSet after removal
        System.out.println("LinkedHashSet after removing "
                           + "elements: " + set);
    }
}
```

**输出:**

```java
LinkedHashSet: [Welcome, To, Geeks, 4]
LinkedHashSet after removing elements: [To]

```