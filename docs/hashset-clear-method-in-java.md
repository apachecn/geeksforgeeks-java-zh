# Java 中的 HashSet clear()方法

> 原文:[https://www.geeksforgeeks.org/hashset-clear-method-in-java/](https://www.geeksforgeeks.org/hashset-clear-method-in-java/)

Java.util.HashSet.clear()方法用于从 HashSet 中移除所有元素。使用 clear()方法只会清除集合中的所有元素，而不会删除集合。换句话说，我们可以说 clear()方法只用于清空一个现有的 HashSet。

**语法:**

```
Hash_Set.clear()
```

**参数:**该方法不取任何参数

**返回值:**函数不返回值。

下面程序举例说明了

```
// Java code to illustrate clear()
import java.io.*;
import java.util.HashSet;

public class HashSetDemo{
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

        // Clearing the HashSet using clear() method
        set.clear();

        // Displaying the final Set after clearing;
        System.out.println("The final set: " + set);
    }
}
```

**方法:**

```
HashSet: [4, Geeks, Welcome, To]
The final set: []

```