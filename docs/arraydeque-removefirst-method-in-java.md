# Java 中的 ArrayDeque removeFirst()方法

> 原文:[https://www . geeksforgeeks . org/arraydeque-remove first-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-removefirst-method-in-java/)

**Java . util . arraydeque . remove first()**方法用于移除 Deque 的第一个元素。

**语法:**

```
Array_Deque.removeFirst()
```

**参数:**该方法不取任何参数。

**返回值:**此方法返回去重后的第一个元素。

**异常:**方法抛出 *NoSuchElementException* 如果 deque 为空则抛出。

下面的程序说明了 Java . util . Arraydeque . remove first()方法:

**程序 1:**

```
// Java code to illustrate removeFirst()
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

        // Removing elements using removeFirst() method
        de_que.removeFirst();
        de_que.removeFirst();
        de_que.removeFirst();

        // Displaying the ArrayDeque after removal
        System.out.println("ArrayDeque after removing "
                           + "elements: " + de_que);
    }
}
```

**Output:**

```
Initial ArrayDeque: [Welcome, To, Geeks, For, Geeks]
ArrayDeque after removing elements: [For, Geeks]

```

**程序 2:**

```
// Java code to illustrate removeFirst()
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

        // Removing elements using removeFirst() method
        de_que.removeFirst();
        de_que.removeFirst();

        // Displaying the ArrayDeque after removal
        System.out.println("ArrayDeque after removing "
                           + "elements: " + de_que);
    }
}
```

**Output:**

```
Initial ArrayDeque: [10, 15, 30, 20, 5]
ArrayDeque after removing elements: [30, 20, 5]

```