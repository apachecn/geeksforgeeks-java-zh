# Java 中的数组大小()方法

> 原文:[https://www . geesforgeks . org/arraydeque-size-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-size-method-in-java/)

Java 中的 Java.util.ArrayDeque.size()方法用于获取 Deque 的大小或 Deque 中存在的元素数量。

**语法:**

```java
Array_Deque.size()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回德格中存在的元素的大小或数量。

下面的程序说明了 Java.util.ArrayDeque.size()方法:
**程序 1:** 将字符串元素添加到 Deque 中。

```java
// Java code to illustrate size()
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

        // Displaying the size of Deque
        System.out.println("The size is: " + de_que.size());
    }
}
```

**Output:**

```java
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
The size is: 5

```

**程序 2:** 将整数元素加入到德格中。

```java
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

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);

        // Displaying the size of Deque
        System.out.println("The size is: " + de_que.size());
    }
}
```

**Output:**

```java
ArrayDeque: [10, 15, 30]
The size is: 3

```