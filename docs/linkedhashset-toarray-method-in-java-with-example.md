# 用示例

将 Java 中的方法链接到数组

> 原文:[https://www . geeksforgeeks . org/linked hashset-to array-method-in-Java-with-example/](https://www.geeksforgeeks.org/linkedhashset-toarray-method-in-java-with-example/)

**Java LinkedHashSet** 的 **toArray()** 方法用于形成一个与 LinkedHashSet 相同元素的数组。基本上，它会将 LinkedHashSet 中的所有元素复制到一个新数组中。

**语法:**

```java
Object[] arr = LinkedHashSet.toArray()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个数组，该数组包含类似于 LinkedHashSet 的元素。

下面的程序说明了 LinkedHashSet.toArray()方法:

**程序 1:**

```java
// Java code to illustrate toArray()

import java.util.*;

public class LinkedHashSetDemo {
    public static void main(String args[])
    {
        // Creating an empty LinkedHashSet
        LinkedHashSet<String>
            set = new LinkedHashSet<String>();

        // Use add() method to add
        // elements into the LinkedHashSet
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("For");
        set.add("Geeks");

        // Displaying the LinkedHashSet
        System.out.println("The LinkedHashSet: "
                           + set);

        // Creating the array and using toArray()
        Object[] arr = set.toArray();

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The LinkedHashSet: [Welcome, To, Geeks, For]
The array is:
Welcome
To
Geeks
For

```

**程序 2:**

```java
// Java code to illustrate toArray()

import java.util.*;

public class LinkedHashSetDemo {
    public static void main(String args[])
    {
        // Creating an empty LinkedHashSet
        LinkedHashSet<Integer>
            set = new LinkedHashSet<Integer>();

        // Use add() method to add
        // elements into the LinkedHashSet
        set.add(10);
        set.add(15);
        set.add(30);
        set.add(20);
        set.add(5);
        set.add(25);

        // Displaying the LinkedHashSet
        System.out.println("The LinkedHashSet: "
                           + set);

        // Creating the array and using toArray()
        Object[] arr = set.toArray();

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The LinkedHashSet: [10, 15, 30, 20, 5, 25]
The array is:
10
15
30
20
5
25

```