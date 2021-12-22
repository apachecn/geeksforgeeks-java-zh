# Java 中的 ArrayDeque pollFirst()方法

> 原文:[https://www . geeksforgeeks . org/arraydeque-poll first-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-pollfirst-method-in-java/)

java 中的 java.util.ArrayDeque.pollFirst()方法用于检索或获取并移除 Deque 的第一个元素。peekFirst()方法只检索了第一个元素，但是 pollFirst()也在检索的同时删除了该元素。如果目标为空，则返回空。

**语法:**

```java
Array_Deque.pollFirst()
```

**参数:**该方法不取任何参数。

**返回值:**该方法删除了 Deque 的第一个元素，并返回相同的值。如果目标为空，则返回空。

下面的程序说明了 Java . util . arraydeque . pollsfirst()方法:
**程序 1:**

```java
// Java code to illustrate pollFirst()
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

        // Displaying the first element
        System.out.println("The element at head is: " + 
                                     de_que.pollFirst());

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
// Java code to illustrate pollFirst()
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

        // Displaying the first element
        System.out.println("The element at head is: " + 
                                    de_que.pollFirst());

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
// Java code to illustrate pollFirst()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<Integer> de_que = new ArrayDeque<Integer>();

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);

        // Displaying the first
        System.out.println("The element at head is: " + 
                                      de_que.pollFirst());
    }
}
```

**Output:**

```java
ArrayDeque: []
The element at head is: null

```