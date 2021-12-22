# Java 中的 HashSet 克隆()方法

> 原文:[https://www.geeksforgeeks.org/hashset-clone-method-in-java/](https://www.geeksforgeeks.org/hashset-clone-method-in-java/)

Java.util.HashSet.clone()方法用于返回所述哈希集的浅层副本。它只是创建了一个集合的副本。

**语法:**

```
Hash_Set.clone()
```

**参数:**该方法不取任何参数。

**返回值:**方法只是返回一个 HashSet 的副本。

下面程序举例说明了

```
// Java code to illustrate clone()
import java.io.*;
import java.util.HashSet;

public class Hash_Set_Demo {
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

        // Creating a new cloned set
        HashSet cloned_set = new HashSet();

        // Cloning the set using clone() method
        cloned_set = (HashSet)set.clone();

        // Displaying the new Set after Cloning;
        System.out.println("The new set: " + cloned_set);
    }
}
```

**输出:**

```
HashSet: [4, Geeks, Welcome, To]
The new set: [Geeks, Welcome, To, 4]

```

方法