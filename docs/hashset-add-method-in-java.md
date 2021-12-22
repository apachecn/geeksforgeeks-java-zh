# Java 中的 HashSet add()方法

> 原文:[https://www.geeksforgeeks.org/hashset-add-method-in-java/](https://www.geeksforgeeks.org/hashset-add-method-in-java/)

Java HashSet 中的 Java.util.HashSet.add()方法用于将特定元素添加到 HashSet 中。只有当指定的元素不在哈希集中时，此方法才会添加元素，否则，如果元素已经在哈希集中，函数将返回 False。

**语法:**

```java
Hash_Set.add(Object element)
```

**参数:**参数*元素*属于 HashSet 类型，是指要添加到集合中的元素。

**返回值:**如果元素不在哈希集中，函数返回真；如果元素已经在哈希集中，函数返回假。

下面程序举例说明了

```java
// Java code to illustrate add()
import java.io.*;
import java.util.HashSet;

public class HashSetDemo {
    public static void main(String args[])
    {
        // Creating an empty HashSet
        HashSet<String> set = new HashSet<String>();

        // Use add() method to add elements into the Set
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("4");
        set.add("Geeks");

        // Displaying the HashSet
        System.out.println("HashSet: " + set);
    }
}
```

**输出:**

```java
HashSet: [4, Geeks, Welcome, To]

```