# Java 中的 LinkedList clear()方法

> 原文:[https://www . geesforgeks . org/linked list-clear-method-in-Java/](https://www.geeksforgeeks.org/linkedlist-clear-method-in-java/)

Java.util.LinkedList.clear()方法用于从链表中移除所有元素。使用 clear()方法只会清除列表中的所有元素，而不会删除列表。换句话说，我们可以说 clear()方法仅用于清空现有的 LinkedList。

**语法:**

```
void clear()

```

**参数:**此功能不接受任何参数。

**返回值:**此方法不返回值。

下面的程序说明了 Java.util.LinkedList.clear()方法:

```
// Java code to illustrate boolean clear()
import java.io.*;
import java.util.LinkedList;

public class LinkedListDemo {
    public static void main(String args[])
    {

        // Creating an empty LinkedList
        LinkedList<String> list = new LinkedList<String>();

        // Using add() method to add elements in the list
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        list.add("10");
        list.add("20");

        // Displaying the List
        System.out.println("Original LinkedList:" + list);

        // Clearing the list
        list.clear();

        // Accessing the List after clearing it
        System.out.println("List after clearing all elements: " + list);

        // Adding elements after clearing the list
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");

        // Displaying the List
        System.out.println("After adding elements to empty list:" + list);
    }
}
```

输出:

```
Original LinkedList:[Geeks, for, Geeks, 10, 20]
List after clearing all elements: []
After adding elements to empty list:[Geeks, for, Geeks]

```