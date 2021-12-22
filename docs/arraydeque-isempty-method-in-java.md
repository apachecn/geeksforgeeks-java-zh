# Java 中的 ArrayDeque isEmpty()方法

> 原文:[https://www . geesforgeks . org/arraydeque-isempty-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-isempty-method-in-java/)

Java 中的 Java.util.ArrayDeque.isEmpty()方法用于检查和验证 ArrayDeque 是否为空。如果目标为空，则返回真，否则返回假。

**语法:**

```
Array_Deque.isEmpty()
```

**参数:**该方法不取任何参数。

**返回值:**如果目标为空，函数返回真，否则返回假。

下面的程序说明了 Java.util.ArrayDeque.isEmpty()方法:

**程序 1:**

```
// Java code to illustrate isEmpty()
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

        // Verifying if the Deque is empty or not
        System.out.println("The Deque is empty? " + 
                                    de_que.isEmpty());

        // Clearing the deque
        de_que.clear();

        // Verifying if the Deque is empty or not
        System.out.println("The Deque is empty? " + 
                                    de_que.isEmpty());
    }
}
```

**Output:**

```
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
The Deque is empty? false
The Deque is empty? true

```

**程序 2:**

```
// Java code to illustrate isEmpty()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<Integer> de_que = new ArrayDeque<Integer>();

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);

        // Verifying if the Deque is empty or not
        System.out.println("The Deque is empty? " + 
                                   de_que.isEmpty());
    }
}
```

**Output:**

```
ArrayDeque: []
The Deque is empty? true

```