# Java 中的 LinkedList addFirst()方法

> 原文:[https://www . geesforgeks . org/linked list-add first-method-in-Java/](https://www.geeksforgeeks.org/linkedlist-addfirst-method-in-java/)

java 中的 java.util.LinkedList.addFirst()方法用于在 LinkedList 的开头插入特定的元素。

**语法:**

```java
void addFirst(Object element)

```

**参数:**该函数接受单个参数*元素*，如上语法所示。此参数指定的元素附加在列表的开头。

**返回值:**此方法不返回值。

下面的程序说明了 java.util.LinkedList.addFirst()方法:

```java
// Java code to illustrate addFirst() method of class LinkedList

import java.io.*;
import java.util.LinkedList;

public class LinkedListDemo {
    public static void main(String args[])
    {

        // creating an empty LinkedList
        LinkedList<String> list = new LinkedList<String>();

        // use add() method to add elements in the list
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        list.add("10");
        list.add("20");

        // Output the present list
        System.out.println("The list is:" + list);

        // Adding new elements at the beginning
        list.addFirst("First");
        list.addFirst("At");

        // Displaying the new list
        System.out.println("The new List is:" + list);
    }
}
```

**输出:**

```java
The list is:[Geeks, for, Geeks, 10, 20]
The new List is:[At, First, Geeks, for, Geeks, 10, 20]

```