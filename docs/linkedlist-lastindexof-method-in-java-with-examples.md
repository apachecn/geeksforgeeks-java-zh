# 用示例链接 Java 中的 lastIndexOf()方法列表

> 原文:[https://www . geeksforgeeks . org/linked list-last indexof-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedlist-lastindexof-method-in-java-with-examples/)

存在于 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中的[链接列表类](https://www.geeksforgeeks.org/linked-list-in-java/)的 *lastIndexOf(Object element)方法*用于检查和查找列表中特定元素的出现。如果该元素出现在列表中，则 lastIndexOf()方法返回该元素最后一次出现的索引，否则返回-1。此方法用于查找 LinkedList 中特定元素的最后一次出现。

**语法:**

```java
LinkedList.lastIndexOf(Object element)
```

**参数:**参数*元素*属于链接列表类型。

> 它指的是需要检查最后一次出现的元素。

**返回值:**元素在列表中最后一次出现的位置，否则如果该元素不在列表中，则该方法返回-1。返回值是整数类型。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate lastIndexOf() Method
// of LinkedList class

// Importing required classes
import java.io.*;
import java.util.LinkedList;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Creating an empty LinkedList of string type
        LinkedList<String> list = new LinkedList<String>();

        // Adding elements in the list
        // using add() method
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        list.add("10");
        list.add("20");

        // Displaying the current elements inside LinkedList
        System.out.println("LinkedList:" + list);

        // The last position of an element is returned
        // using lastIndexOf() method and
        // displaying on the console
        System.out.println(
            "Last occurrence of Geeks is at index: "
            + list.lastIndexOf("Geeks"));
        System.out.println(
            "Last occurrence of 10 is at index: "
            + list.lastIndexOf("10"));
    }
}
```

**Output:** 

```java
LinkedList:[Geeks, for, Geeks, 10, 20]
Last occurrence of Geeks is at index: 2
Last occurrence of 10 is at index: 3
```