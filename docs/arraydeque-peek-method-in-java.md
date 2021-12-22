# Java 中的 ArrayDeque peek()方法

> 原文:[https://www . geesforgeks . org/arraydeque-peek-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-peek-method-in-java/)

java 中的 java.util.ArrayDeque.peek()方法用于检索或获取 Deque 头部的元素。检索到的元素不会被删除或从队列中移除，方法只是返回它。如果 deque 中没有元素，则返回空值。

**语法:**

```java
Array_Deque.peek()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回 Deque 头部的元素。

下面的程序说明了 Java.util.ArrayDeque.peek()方法:
**程序 1:**

```java
// Java code to illustrate peek()
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
        System.out.println("Initial ArrayDeque: " + de_que);

        // Displaying the head
        System.out.println("The element at head is: " + 
                                           de_que.peek());

        // Displaying the ArrayDeque after operation
        System.out.println("Final ArrayDeque: " + de_que);
    }
}
```

**Output:**

```java
Initial ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
The element at head is: Welcome
Final ArrayDeque: [Welcome, To, Geeks, 4, Geeks]

```

**程序 2:**

```java
// Java code to illustrate peek()
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
        System.out.println("Initial ArrayDeque: " + de_que);

        // Displaying the head
        System.out.println("The element at head is: " + 
                                           de_que.peek());

        // Displaying the ArrayDeque after operation
        System.out.println("Final ArrayDeque: " + de_que);
    }
}
```

**Output:**

```java
Initial ArrayDeque: [10, 15, 30, 20, 5]
The element at head is: 10
Final ArrayDeque: [10, 15, 30, 20, 5]

```

**程序 3:** 对于空车:

```java
// Java code to illustrate peek()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        ArrayDeque<Integer> de_que = new ArrayDeque<Integer>();

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);

        // Displaying the head
        System.out.println("The element at head is: " + de_que.peek());
    }
}
```

**Output:**

```java
ArrayDeque: []
The element at head is: null

```