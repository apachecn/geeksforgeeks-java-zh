# Java 中 LinkedList indexOf()方法

> 原文:[https://www . geesforgeks . org/linked list-indexof-method-in-Java/](https://www.geeksforgeeks.org/linkedlist-indexof-method-in-java/)

方法用于检查和查找列表中特定元素的出现。如果该元素存在，则返回该元素第一次出现的索引，否则，如果列表不包含该元素，则返回-1。

**语法:**

```java
LinkedList.indexOf(Object element)
```

**参数:**参数*元素*属于链接列表类型。它指定需要在链接列表中检查其出现的元素。

**返回值:**如果列表中不存在*元素*，则该方法返回列表中第一个出现的*元素*的索引或位置。返回值是整数类型。

下面程序举例说明了 Java.util.LinkedList.indexOf()方法:

```java
// Java code to illustrate indexOf()
import java.io.*;
import java.util.LinkedList;

public class LinkedListDemo {
   public static void main(String args[]) {

      // Creating an empty LinkedList
      LinkedList<String> list = new LinkedList<String>();

      // Use add() method to add elements in the list
      list.add("Geeks");
      list.add("for");
      list.add("Geeks");
      list.add("10");
      list.add("20");

      // Displaying the list
      System.out.println("LinkedList:" + list);

      // The first position of an element 
      // is returned
      System.out.println("The first occurrence of Geeks is at index:" 
                                              + list.indexOf("Geeks"));
      System.out.println("The first occurrence of 10 is at index: "  
                                               + list.indexOf("10"));

   }
}
```

**输出:**

```java
LinkedList:[Geeks, for, Geeks, 10, 20]
The first occurrence of Geeks is at index: 0
The first occurrence of 10 is at index: 3

```