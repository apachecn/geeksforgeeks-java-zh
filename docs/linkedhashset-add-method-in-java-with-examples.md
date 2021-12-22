# 用示例链接 Java 中的 add()方法

> 原文:[https://www . geeksforgeeks . org/link edhashset-add-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedhashset-add-method-in-java-with-examples/)

Java LinkedHashSet 中的 add()方法用于将特定元素添加到 LinkedHashSet 中。只有当指定的元素不在 LinkedHashSet 中时，此方法才会添加该元素，否则，如果该元素已经存在于 LinkedHashSet 中，函数将返回 False。

**语法:**

```java
Hash_Set.add(Object element)
```

**参数:**参数*元素*的类型为 LinkedHashSet，是指要添加到集合中的元素。

**返回值:**如果该元素不在 LinkedHashSet 中，则函数返回 True 否则，如果该元素已经在 LinkedHashSet 中，则函数返回 False。

下面程序举例说明了

```java
// Java code to illustrate add()
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
    }
}
```

**输出:**

```java
LinkedHashSet: [Welcome, To, Geeks, 4]

```