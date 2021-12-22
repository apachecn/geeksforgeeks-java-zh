# Java 中的 HashSet isEmpty()方法

> 原文:[https://www . geesforgeks . org/hashset-isempty-method-in-Java/](https://www.geeksforgeeks.org/hashset-isempty-method-in-java/)

Java.util.HashSet.isEmpty()方法用于检查 HashSet 是否为空。如果哈希表为空，则返回真，否则返回假。

**语法:**

```
Hash_Set.isEmpty()
```

**参数:**该方法不取任何参数

**返回值:**如果集合为空，函数返回真，否则返回假。

下面程序举例说明了

```
// Java code to illustrate contains()
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

```
HashSet: [4, Geeks, Welcome, To]
Is the set empty: false
Is the set empty: true

```

方法