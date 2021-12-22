# Java 中的 LinkedList size()方法

> 原文:[https://www . geesforgeks . org/linked list-size-method-in-Java/](https://www.geeksforgeeks.org/linkedlist-size-method-in-java/)

Java.util.LinkedList.size()方法用于获取链表的大小或链表中存在的元素数量。

**语法:**

```java
LinkedList.size()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回链表中元素的大小或数量。

下面程序举例说明了

```java
// Java code to illustrate size()
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

        // Displaying the linkedlist
        System.out.println("LinkedList:" + list);

        // Displaying the size of the list
        System.out.println("The size of the linked list is: " 
                                                + list.size());
    }
}
```

**方法:**

```java
LinkedList:[Geeks, for, Geeks, 10, 20]
The size of the linked list is: 5

```