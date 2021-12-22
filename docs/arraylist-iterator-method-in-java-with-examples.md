# Java 中的数组列表迭代器()方法，示例

> 原文:[https://www . geesforgeks . org/ArrayList-iterator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/arraylist-iterator-method-in-java-with-examples/)

**Java 集合框架**中**数组列表类**的**迭代器()**方法用于以适当的顺序获取该列表中元素的迭代器。返回的迭代器是快速失败的。

**语法:**

```java
 Iterator iterator()
```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个**迭代器**在这个列表中的元素上以适当的顺序

下面的例子说明了 ArrayList.iterator()方法:

**程序 1:**

```java
// Java code to illustrate iterator()

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // Create and populate the list
        ArrayList<String> list
            = new ArrayList<>();

        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        list.add("is");
        list.add("a");
        list.add("CS");
        list.add("Students");
        list.add("Portal");

        // Displaying the list
        System.out.println("The list is: \n"
                           + list);

        // Create an iterator for the list
        // using iterator() method
        Iterator<String> iter
            = list.iterator();

        // Displaying the values after iterating
        // through the list
        System.out.println("\nThe iterator values"
                           + " of list are: ");
        while (iter.hasNext()) {
            System.out.print(iter.next() + " ");
        }
    }
}
```

**Output:**

```java
The list is: 
[Geeks, for, Geeks, is, a, CS, Students, Portal]

The iterator values of list are: 
Geeks for Geeks is a CS Students Portal

```

**程序 2:**

```java
// Java code to illustrate iterator()

import java.util.*;

public class GFG {

    public static void main(String args[])
    {
        // Creating an empty ArrayList
        ArrayList<Integer> list
            = new ArrayList<Integer>();

        // Use add() method to add
        // elements into the list
        list.add(10);
        list.add(15);
        list.add(30);
        list.add(20);
        list.add(5);

        // Displaying the list
        System.out.println("The list is: \n"
                           + list);

        // Create an iterator for the list
        // using iterator() method
        Iterator<Integer> iter = list.iterator();

        // Displaying the values
        // after iterating through the list
        System.out.println("\nThe iterator values"
                           + " of list are: ");
        while (iter.hasNext()) {
            System.out.print(iter.next() + " ");
        }
    }
}
```

**Output:**

```java
The list is: 
[10, 15, 30, 20, 5]

The iterator values of list are: 
10 15 30 20 5

```