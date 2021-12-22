# Java 中的 LinkedList getLast()方法

> 原文:[https://www . geesforgeks . org/linked list-get last-method-in-Java/](https://www.geeksforgeeks.org/linkedlist-getlast-method-in-java/)

链表是 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中[集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的一部分。这个类是[链接列表数据结构](https://www.geeksforgeeks.org/data-structures/linked-list/)的实现，它是一个线性数据结构，其中元素不存储在连续的位置，每个元素都是一个单独的对象，有一个数据部分和。Java.util.LinkedList.getLast()方法用于从 LinkedList 中获取或检索最后一个元素或列表尾部的元素。

![](img/b8b33a92c00d059e80ecc5b62687a143.png)

插图:

```
Input : 4 --> 1 --> 5 --> 6 --> 1 --> 3
Output: 3
```

众所周知，getLast()是 [LinekdList 类中已经存在的方法之一。](https://www.geeksforgeeks.org/linked-list-in-java/)它从 LinkedList 的元素所在的对象中检索最后一个元素。正如我们所知，LinkedList 是存在于 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中的一个类，因此，如果我们操作以下方法，语法将如下所示:

```
import java.util.LinkedList;
LinkedList ll = new LinkedList<T>();  
ll.getLast();
```

简单地说，如果我们想知道 LinkedList 的最后一个元素或尾部，那么请执行下面列出的检查。稍后，它将作为一个示例在实现时进行说明。

**语法:**

```
LinkedList.getLast();
```

**返回类型:**列表尾部的最后一个元素或元素。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate getLast() method

// Importing required classes
import java.io.*;
import java.util.LinkedList;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Creating an empty LinkedList class object
        // Declaring object of string type
        LinkedList<String> list = new LinkedList<String>();

        // Adding elements in the list
        // using add() method
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        list.add("10");
        list.add("20");

        // Displaying all elements of LinekdList
        System.out.println("LinkedList:" + list);

        // Now from these elements procuring
        // last element from the list
        // using getLast() method
        System.out.println("The last element is: "
                           + list.getLast());
    }
}
```

**Output:** 

```
LinkedList:[Geeks, for, Geeks, 10, 20]
The last element is: 20
```