# Java 中的 ArrayDeque poll()方法

> 原文:[https://www . geesforgeks . org/arraydeque-poll-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-poll-method-in-java/)

java 中的 java.util.ArrayDeque.poll()方法用于检索或获取并移除出现在 Deque 头部的元素。peek()方法只在头部检索到元素，但是 poll()也会在检索的同时移除元素。如果目标为空，则返回空。

**语法:**

```java
Array_Deque.poll()
```

**参数:**该方法不取任何参数。

**返回值:**该方法删除了 Deque 头部的元素，并返回相同的值。如果目标为空，则返回空。

下面的程序说明了 Java.util.ArrayDeque.poll()方法:
**程序 1:**

```java
// Java code to illustrate poll()
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

        // Displaying the head
        System.out.println("The element at head is: " 
                                           + de_que.poll());

        // Displaying the final ArrayDeque
        System.out.println("ArrayDeque after operation: " 
                                                   + de_que);
    }
}
```

**Output:**

```java
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
The element at head is: Welcome
ArrayDeque after operation: [To, Geeks, 4, Geeks]

```

**程序 2:**

```java
// Java code to illustrate poll()
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

        // Displaying the head
        System.out.println("The element at head is: " 
                                         + de_que.poll());

        // Displaying the final ArrayDeque
        System.out.println("ArrayDeque after operation: "
                                                 + de_que);
    }
}
```

**Output:**

```java
ArrayDeque: [10, 15, 30, 20, 5]
The element at head is: 10
ArrayDeque after operation: [15, 30, 20, 5]

```

**程序 3:** 对于空车:

```java
// Java code to illustrate poll()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<Integer> de_que = new ArrayDeque<Integer>();

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);

        // Displaying the head
        System.out.println("The element at head is: " + 
                                           de_que.poll());
    }
}
```

**Output:**

```java
ArrayDeque: []
The element at head is: null

```