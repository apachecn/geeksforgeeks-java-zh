# Java 中的 concurrentlinkedequepeek()方法，示例

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-peek-method-in-Java-with-example/](https://www.geeksforgeeks.org/concurrentlinkeddeque-peek-method-in-java-with-example/)

java 中的 Java . util . concurrentlinkedrequest . peek()方法用于检索或获取 Deque 头部的元素。检索到的元素不会被删除或从 Deque 中移除，相反，该方法只是返回它。如果 deque 中没有元素，则返回空值。

**语法:**

```java
Array_Deque.peek()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回 Deque 头部的元素。

下面的程序举例说明了 Java . util . concurrentlinkedrequest . peek()方法:

**程序 1:**

```java
// Java code to illustrate peek()

import java.util.concurrent.*;

public class ConcurrentLinkedDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ConcurrentLinkedDeque
        ConcurrentLinkedDeque<String> de_que
            = new ConcurrentLinkedDeque<String>();

        // Use add() method to add elements into the Deque
        de_que.add("Welcome");
        de_que.add("To");
        de_que.add("Geeks");
        de_que.add("4");
        de_que.add("Geeks");

        // Displaying the ConcurrentLinkedDeque
        System.out.println("Initial ConcurrentLinkedDeque: "
                           + de_que);

        // Displaying the head
        System.out.println("The element at head is: "
                           + de_que.peek());

        // Displaying the ConcurrentLinkedDeque after operation
        System.out.println("Final ConcurrentLinkedDeque: "
                           + de_que);
    }
}
```

**Output:**

```java
Initial ConcurrentLinkedDeque: [Welcome, To, Geeks, 4, Geeks]
The element at head is: Welcome
Final ConcurrentLinkedDeque: [Welcome, To, Geeks, 4, Geeks]

```

**程序 2:**

```java
// Java code to illustrate peek()
import java.util.concurrent.*;

public class ConcurrentLinkedDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ConcurrentLinkedDeque
        ConcurrentLinkedDeque<Integer> de_que
            = new ConcurrentLinkedDeque<Integer>();

        // Use add() method to add elements into the Deque
        de_que.add(10);
        de_que.add(15);
        de_que.add(30);
        de_que.add(20);
        de_que.add(5);

        // Displaying the ConcurrentLinkedDeque
        System.out.println("Initial ConcurrentLinkedDeque: "
                           + de_que);

        // Displaying the head
        System.out.println("The element at head is: "
                           + de_que.peek());

        // Displaying the ConcurrentLinkedDeque after operation
        System.out.println("Final ConcurrentLinkedDeque: "
                           + de_que);
    }
}
```

**Output:**

```java
Initial ConcurrentLinkedDeque: [10, 15, 30, 20, 5]
The element at head is: 10
Final ConcurrentLinkedDeque: [10, 15, 30, 20, 5]

```

**程序 3:** 对于空车:

```java
// Java code to illustrate peek()
import java.util.concurrent.*;

public class ConcurrentLinkedDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ConcurrentLinkedDeque
        ConcurrentLinkedDeque<Integer> de_que
            = new ConcurrentLinkedDeque<Integer>();

        // Displaying the ConcurrentLinkedDeque
        System.out.println("ConcurrentLinkedDeque: "
                           + de_que);

        // Displaying the head
        System.out.println("The element at head is: "
                           + de_que.peek());
    }
}
```

**Output:**

```java
ConcurrentLinkedDeque: []
The element at head is: null

```