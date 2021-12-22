# Java 中的 ArrayDeque 迭代器()方法

> 原文:[https://www . geesforgeks . org/arraydeque-iterator-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-iterator-method-in-java/)

Java.util.ArrayDeque.iterator()方法用于返回 ArrayDeque 元素的迭代器。

**语法:**

```java
Iterator iterate_value = Array_Deque.iterator();
```

**参数:**该方法不取任何参数。

**返回值:**该方法迭代 deque 的元素并返回值(迭代器)。

下面的程序说明了 Java.util.ArrayDeque.iterator()方法:
**程序 1:**

```java
// Java code to illustrate iterator()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<String> de_que = new ArrayDeque<String>();

        // Use add() method to add elements into the Queue
        de_que.add("Welcome");
        de_que.add("To");
        de_que.add("Geeks");
        de_que.add("4");
        de_que.add("Geeks");

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);

        // Creating an iterator
        Iterator value = de_que.iterator();

        // Displaying the values after iterating through the Deque
        System.out.println("The iterator values are: ");
        while (value.hasNext()) {
            System.out.println(value.next());
        }
    }
}
```

**Output:**

```java
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
The iterator values are: 
Welcome
To
Geeks
4
Geeks

```

**程序 2:**

```java
// Java code to illustrate iterator()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<Integer> de_que = new ArrayDeque<Integer>();

        // Use add() method to add elements into the Queue
        de_que.add(10);
        de_que.add(15);
        de_que.add(30);
        de_que.add(20);
        de_que.add(5);

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);

        // Creating an iterator
        Iterator value = de_que.iterator();

        // Displaying the values after iterating through the Deque
        System.out.println("The iterator values are: ");
        while (value.hasNext()) {
            System.out.println(value.next());
        }
    }
}
```

**Output:**

```java
ArrayDeque: [10, 15, 30, 20, 5]
The iterator values are: 
10
15
30
20
5

```