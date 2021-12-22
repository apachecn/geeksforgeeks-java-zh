# Java 中的 HashSet size()方法

> 原文:[https://www.geeksforgeeks.org/hashset-size-method-in-java/](https://www.geeksforgeeks.org/hashset-size-method-in-java/)

Java.util.HashSet.size()方法用于获取 HashSet 的大小或 HashSet 中存在的元素数量。

**语法:**

```java
Hash_Set.size()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回哈希表中元素的大小或数量。

下面程序举例说明了

```java
// Java code to illustrate HashSet.size() method
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

        // Displaying the size of the HashSet
        System.out.println("The size of the set is: " + set.size());
    }
}
```

**方法:**

```java
HashSet: [4, Geeks, Welcome, To]
The size of the set is: 4

```