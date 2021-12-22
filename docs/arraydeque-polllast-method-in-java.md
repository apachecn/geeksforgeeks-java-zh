# Java 中的 ArrayDeque pollLast()方法

> 原文:[https://www . geesforgeks . org/arraydeque-poll last-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-polllast-method-in-java/)

java 中的 Java . util . arraydeque . pollast()方法用于检索或获取并移除 Deque 的最后一个元素。peekLast()方法只在最后检索到元素，但是 pollLast()也会在检索的同时移除元素。如果目标为空，则返回空。

**语法:**

```java
Array_Deque.pollLast()
```

**参数:**该方法不取任何参数。

**返回值:**该方法删除了 Deque 的最后一个元素，并返回相同的值。如果目标为空，则返回空。

下面的程序说明了 Java . util . arraydeque . pollast()方法:
**程序 1:**

```java
// Java code to illustrate pollLast()
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
        de_que.add("4");
        de_que.add("Geeks");

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);

        // Displaying the last element
        System.out.println("The last element is: " +
                                    de_que.pollLast());

        // Displaying the final ArrayDeque
        System.out.println("ArrayDeque after operation: "
                                                + de_que);
    }
}
```

**Output:**

```java
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
The last element is: Geeks
ArrayDeque after operation: [Welcome, To, Geeks, 4]

```

**程序 2:**

```java
// Java code to illustrate pollLast()
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
        System.out.println("ArrayDeque: " + de_que);

        // Displaying the last element
        System.out.println("The element at head is: " +
                                       de_que.pollLast());

        // Displaying the final ArrayDeque
        System.out.println("ArrayDeque after operation: "
                                                + de_que);
    }
}
```

**Output:**

```java
ArrayDeque: [10, 15, 30, 20, 5]
The element at head is: 5
ArrayDeque after operation: [10, 15, 30, 20]

```

**程序 3:** 对于空车:

```java
// Java code to illustrate pollLast()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<Integer> de_que = new ArrayDeque<Integer>();

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);

        // Displaying the last element
        System.out.println("The element at head is: " +
                                       de_que.pollLast());
    }
}
```

**Output:**

```java
ArrayDeque: []
The element at head is: null

```