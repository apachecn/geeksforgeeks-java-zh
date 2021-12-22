# Java 中的 LinkedList removeFirst()方法

> 原文:[https://www . geesforgeks . org/linked list-remove first-method-in-Java/](https://www.geeksforgeeks.org/linkedlist-removefirst-method-in-java/)

Java . util . LinkedList . removeFirst()方法用于从链接列表中移除第一个元素。此函数还返回移除后的第一个元素。

**语法:**

```
LinkedList.removeFirst();

```

**参数:**该功能不取任何参数。

**返回值:**该方法返回列表的第一个元素或位于列表头部的元素。

下面的程序说明了 Java . util . linkedlist . removefirst()方法:

```
// Java code to illustrate removeFirst() method
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

        // Displaying the list
        System.out.println("LinkedList:" + list);

        // Remove the head using removeFirst() method
        System.out.println("The first element is: " + list.removeFirst());

        // Displaying the final list
        System.out.println("Final LinkedList:" + list);
    }
}
```

**输出:**

```
LinkedList:[Geeks, for, Geeks, 10, 20]
The first element is: Geeks
Final LinkedList:[for, Geeks, 10, 20]

```