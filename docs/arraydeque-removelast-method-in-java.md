# Java 中的 ArrayDeque removeLast()方法

> 原文:[https://www . geesforgeks . org/arraydeque-remove last-in-method-Java/](https://www.geeksforgeeks.org/arraydeque-removelast-method-in-java/)

**Java . util . arraydeque . remove last()**方法用于移除 Deque 的最后一个元素。

**语法:**

```java
Array_Deque.removeLast()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回去重后的最后一个元素。

**异常:**如果德格为空，该方法抛出 *NoSuchElementException* 。

下面的程序说明了 Java . util . Arraydeque . removelast()方法:

**程序 1:**

```java
// Java code to illustrate removeLast()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<String> de_que = new ArrayDeque<String>();

        // Use add() method to add elements into the Deque
        de_que.add("Welcome");
        de_que.add("To");
        de_que.add("Geeks");
        de_que.add("For");
        de_que.add("Geeks");

        // Displaying the ArrayDeque
        System.out.println("Initial ArrayDeque: " + de_que);

        // Removing elements using removeLast() method
        de_que.removeLast();
        de_que.removeLast();
        de_que.removeLast();

        // Displaying the ArrayDeque after removal
        System.out.println("ArrayDeque after removing "
                           + "elements: " + de_que);
    }
}
```

**Output:**

```java
Initial ArrayDeque: [Welcome, To, Geeks, For, Geeks]
ArrayDeque after removing elements: [Welcome, To]

```

**程序 2:**

```java
// Java code to illustrate removeLast()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<Integer> de_que = new ArrayDeque<Integer>();

        // Use add() method to add elements into the Deque
        de_que.add(10);
        de_que.add(15);
        de_que.add(30);
        de_que.add(20);
        de_que.add(5);

        // Displaying the ArrayDeque
        System.out.println("Initial ArrayDeque: " + de_que);

        // Removing elements using removeLast() method
        de_que.removeLast();
        de_que.removeLast();

        // Displaying the ArrayDeque after removal
        System.out.println("ArrayDeque after removing "
                           + "elements: " + de_que);
    }
}
```

**Output:**

```java
Initial ArrayDeque: [10, 15, 30, 20, 5]
ArrayDeque after removing elements: [10, 15, 30]

```