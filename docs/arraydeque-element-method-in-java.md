# Java 中的 ArrayDeque 元素()方法

> 原文:[https://www . geesforgeks . org/arraydeque-element-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-element-method-in-java/)

java 中的 java.util.ArrayDeque.element()方法用于检索或获取 ArrayDeque 的头部。在这个过程中，该方法不会从 deque 中删除元素，而是返回元素。

**语法:**

```java
Array_Deque.element()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回出现在德克尔头部的元素。

下面的程序说明了 Java.util.ArrayDeque.element()方法:
**程序 1:**

```java
// Java code to illustrate ArrayDeque element() method
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        ArrayDeque<String> de_que = new ArrayDeque<String>();

        // Use add() method to add elements into the Deque
        de_que.add("Welcome");
        de_que.add("To");
        de_que.add("Geeks");
        de_que.add("4");
        de_que.add("Geeks");

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);

        // Displaying the head
        System.out.println("The head element is: " + de_que.element());
    }
}
```

**Output:**

```java
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
The head element is: Welcome

```

**程序 2:**

```java
// Java code to illustrate ArrayDeque element() method
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        ArrayDeque<Integer> de_que = new ArrayDeque<Integer>();

        // Use add() method to add elements into the Deque
        de_que.add(10);
        de_que.add(15);
        de_que.add(30);
        de_que.add(20);
        de_que.add(5);

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);

        // Displaying the head
        System.out.println("The head element is: " + de_que.element());
    }
}
```

**Output:**

```java
ArrayDeque: [10, 15, 30, 20, 5]
The head element is: 10

```