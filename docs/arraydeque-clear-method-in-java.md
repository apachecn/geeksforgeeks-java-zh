# Java 中的 ArrayDeque clear()方法

> 原文:[https://www . geesforgeks . org/arraydeque-clear-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-clear-method-in-java/)

Java 中的 Java.util.ArrayDeque.clear()方法用于从 Deque 中移除所有元素。使用 clear()方法只会清除 deque 中的所有元素，而不会删除 deque。换句话说，可以说 clear()方法只用于清空一个现有的 ArrayDeque。

**语法:**

```
Array_Deque.clear()
```

**参数:**该方法不取任何参数。

**返回值:**函数不返回值。

下面的程序说明了 Java.util.ArrayDeque.clear()方法:
**程序 1:**

```
// Java code to illustrate clear()
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

        // Clearing the Deque
        de_que.clear();

        // Displaying the Deque
        System.out.println("ArrayDeque: " + de_que);
    }
}
```

**Output:**

```
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
ArrayDeque: []

```

**程序 2:**

```
// Java code to illustrate clear()
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

        // Clearing the Deque
        de_que.clear();

        // Displaying the Deque
        System.out.println("ArrayDeque: " + de_que);
    }
}
```

**Output:**

```
ArrayDeque: [10, 15, 30, 20, 5]
ArrayDeque: []

```