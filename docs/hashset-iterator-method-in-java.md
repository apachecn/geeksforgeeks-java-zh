# Java 中的 HashSet 迭代器()方法

> 原文:[https://www . geesforgeks . org/hashset-iterator-method-in-Java/](https://www.geeksforgeeks.org/hashset-iterator-method-in-java/)

Java.util.HashSet.iterator()方法用于返回与哈希集元素相同的迭代器。元素从哈希集中随机返回。

**语法:**

```
Iterator *iterate_value* = Hash_Set.iterator();

```

**参数:**函数不取任何参数。

**返回值:**该方法迭代哈希集的元素并返回值(迭代器)。

下面的程序说明了 Java.util.HashSet.iterator()方法:

```
// Java code to illustrate iterator()
import java.util.*;
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

        // Creating an iterator
        Iterator value = set.iterator();

        // Displaying the values after iterating through the set
        System.out.println("The iterator values are: ");
        while (value.hasNext()) {
            System.out.println(value.next());
        }
    }
}
```

**输出:**

```
HashSet: [4, Geeks, Welcome, To]
The iterator values are: 
4
Geeks
Welcome
To

```