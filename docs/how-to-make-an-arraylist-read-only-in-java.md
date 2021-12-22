# 如何在 Java 中使数组列表只读

> 原文:[https://www . geesforgeks . org/如何制作数组列表-java 只读/](https://www.geeksforgeeks.org/how-to-make-an-arraylist-read-only-in-java/)

给定一个数组列表，任务是使这个数组列表在 Java 中成为只读的。

**示例:**

```java
Input: ArrayList: [1, 2, 3, 4, 5]
Output: Read-only ArrayList: [1, 2, 3, 4, 5] 

Input: ArrayList: [geeks, for, geeks]
Output: Read-only ArrayList: [geeks, for, geeks]

```

在 Collections.unmodifiableList()方法的帮助下，数组列表可以很容易地变成只读的。此方法将可修改的数组列表作为参数，并返回此数组列表的只读不可修改视图。

**语法:**

```java
readOnlyArrayList = Collections.unmodifiableList(ArrayList);
```

下面是上述方法的实现:

```java
// Java program to demonstrate
// unmodifiableList() method

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        try {

            // creating object of ArrayList<Character>
            List<Character> list = new ArrayList<Character>();

            // populate the list
            list.add('X');
            list.add('Y');
            list.add('Z');

            // printing the list
            System.out.println("Initial list: "
                               + list);

            // getting readonly list
            // using unmodifiableList() method
            List<Character>
                immutablelist = Collections
                                    .unmodifiableList(list);

            // printing the list
            System.out.println("ReadOnly ArrayList: "
                               + immutablelist);

            // Adding element to new Collection
            System.out.println("\nTrying to modify"
                               + " the ReadOnly ArrayList.");
            immutablelist.add('A');
        }

        catch (UnsupportedOperationException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Initial list: [X, Y, Z]
ReadOnly ArrayList: [X, Y, Z]

Trying to modify the ReadOnly ArrayList.
Exception thrown : java.lang.UnsupportedOperationException

```