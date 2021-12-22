# LinkedHashSet 在 Java 中包含()方法

> 原文:[https://www . geeksforgeeks . org/link edhashset-contains-method-in-Java/](https://www.geeksforgeeks.org/linkedhashset-contains-method-in-java/)

Java . util . LinkedHashSet . contains()方法用于检查特定元素是否存在于 LinkedHashSet 中。所以它基本上是用来检查一个集合是否包含任何特定的元素。

**语法:**

```
Hash_Set.contains(Object element)
```

**参数:**参数*元素*属于链接哈希集类型。这是需要测试的元素，无论它是否存在于集合中。

**返回值:**如果元素存在于集合中，方法返回真，否则返回假。

下面的程序说明了 Java . util . linkedhashset . contains()方法:

```
// Java code to illustrate LinkedHashSet.contains() method
import java.io.*;
import java.util.LinkedHashSet;

public class LinkedHashSetDemo {
    public static void main(String args[])
    {
        // Creating an empty LinkedHashSet
        LinkedHashSet<String> set = new LinkedHashSet<String>();

        // Using add() method to add elements into the Set
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("4");
        set.add("Geeks");

        // Displaying the LinkedHashSet
        System.out.println("LinkedHashSet: " + set);

        // Check for "Geeks" in the set
        System.out.println("Does the Set contains 'Geeks'? " + set.contains("Geeks"));

        // Check for "4" in the set
        System.out.println("Does the Set contains '4'? " + set.contains("4"));

        // Check if the Set contains "No"
        System.out.println("Does the Set contains 'No'? " + set.contains("No"));
    }
}
```

**输出:**

```
LinkedHashSet: [Welcome, To, Geeks, 4]
Does the Set contains 'Geeks'? true
Does the Set contains '4'? true
Does the Set contains 'No'? false

```