# 链接列表包含 Java 中的()方法

> 原文:[https://www . geesforgeks . org/linked list-contains-method-in-Java/](https://www.geeksforgeeks.org/linkedlist-contains-method-in-java/)

Java.util.LinkedList.contains()方法用于检查链接列表中是否存在元素。它将元素作为参数，如果列表中存在该元素，则返回 True。

**语法:**

```
LinkedList.contains(Object element)
```

**参数:**参数*元素*为链表类型。此参数指的是需要在列表中检查其出现的元素。

**返回值:**如果链接列表中存在*元素*，则该方法返回真，否则返回假。

下面的程序说明了 Java.util.LinkedList.contains()方法:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate boolean contains()
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

      // Output the list
      System.out.println("LinkedList:" + list);

      // Check if the list contains "Hello"
      System.out.println("\nDoes the List contains 'Hello': "
                                      + list.contains("Hello"));

      // Check if the list contains "20"
      System.out.println("Does the List contains '20': "
                                         + list.contains("20"));

      // Check if the list contains "Geeks"
      System.out.println("Does the List contains 'Geeks': "
                                      + list.contains("Geeks"));

   }
}
```

**Output:** 

```
LinkedList:[Geeks, for, Geeks, 10, 20]

Does the List contains 'Hello': false
Does the List contains '20': true
Does the List contains 'Geeks': true
```