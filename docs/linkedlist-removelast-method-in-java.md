# Java 中的 LinkedList removeLast()方法

> 原文:[https://www . geesforgeks . org/linked list-remove last-method-in-Java/](https://www.geeksforgeeks.org/linkedlist-removelast-method-in-java/)

Java . util . LinkedList . remove last()方法用于从 linked list 中移除最后一个元素。此方法还会在移除元素后返回该元素。
**语法:**

```java
LinkedList.removeLast()
```

**参数:**该功能不取任何参数。
**返回值:**该方法返回最后一个元素或列表尾部的元素。
下面的程序说明了 Java . util . linkedlist . removelast()方法:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate removeLast()
import java.io.*;
import java.util.LinkedList;

public class LinkedListDemo {
    public static void main(String args[])
    {
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

        // Remove the tail using removeLast()
        System.out.println("The last element is removed: " + list.removeLast());

        // Displaying the final list
        System.out.println("Final LinkedList:" + list);

        // Remove the tail using removeLast()
        System.out.println("The last element is removed: " + list.removeLast());

        // Displaying the final list
        System.out.println("Final LinkedList:" + list);
    }
}
```

**Output:** 

```java
LinkedList:[Geeks, for, Geeks, 10, 20]
The last element is removed: 20
Final LinkedList:[Geeks, for, Geeks, 10]
The last element is removed: 10
Final LinkedList:[Geeks, for, Geeks]
```

**remove last()的时间复杂度:** : O(1)