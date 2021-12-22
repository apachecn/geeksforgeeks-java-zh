# Java 中的 ArrayDeque pop()方法

> 原文:[https://www . geesforgeks . org/arraydeque-pop-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-pop-method-in-java/)

Java 中的 Java.util.ArrayDeque.pop()方法用于从 Deque 中弹出一个元素。该元素从 deque 的顶部弹出，并从其中移除。

**语法:**

```
Array_Deque.pop()
```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回出现在德格前面的元素。

**异常:**方法抛出 *NoSuchElementException* 如果 deque 为空则抛出。

下面的程序说明了 Java.util.ArrayDeque.pop()方法:
**程序 1:**

```
// Java code to illustrate pop()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<String> de_que = new ArrayDeque<String>();

        // Use add() method to add elements
        de_que.add("Welcome");
        de_que.add("To");
        de_que.add("Geeks");
        de_que.add("For");
        de_que.add("Geeks");

        // Displaying the ArrayDeque
        System.out.println("Initial ArrayDeque: " + de_que);

        // Removing elements using pop() method
        System.out.println("Popped element: " + de_que.pop());
        System.out.println("Popped element: " + de_que.pop());

        // Displaying the ArrayDeque after pop
        System.out.println("Deque after operation "
                           + de_que);
    }
}
```

**Output:**

```
Initial ArrayDeque: [Welcome, To, Geeks, For, Geeks]
Popped element: Welcome
Popped element: To
Deque after operation [Geeks, For, Geeks]

```

**程序 2:**

```
// Java code to illustrate pop()
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

        // Removing elements using pop() method
        System.out.println("Popped element: " + de_que.pop());
        System.out.println("Popped element: " + de_que.pop());

        // Displaying the ArrayDeque after pop
        System.out.println("Deque after operation "
                           + de_que);
    }
}
```

**Output:**

```
Initial ArrayDeque: [10, 15, 30, 20, 5]
Popped element: 10
Popped element: 15
Deque after operation [30, 20, 5]

```