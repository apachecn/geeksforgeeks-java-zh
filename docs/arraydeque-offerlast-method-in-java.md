# Java 中的 ArrayDeque offerLast()方法

> 原文:[https://www . geesforgeks . org/arraydeque-offer last-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-offerlast-method-in-java/)

Java 中的 Java . util . arraydeque . offer last(*Object 元素*)方法用于在这个 Deque 的末尾添加一个特定的元素。功能类似于 Java 中 ArrayDeque 的 [addLast()](https://www.geeksforgeeks.org/arraydeque-addlast-method-in-java/) 、 [add()](https://www.geeksforgeeks.org/arraydeque-add-method-in-java/) 和 offer()方法。

**语法:**

```java
Array_Deque.offerLast(*Object element*)
```

**参数:**参数*元素*的类型为 ArrayDeque，指的是要在 Deque 末尾添加的元素。

**返回值:**如果元素被成功添加到 deque 中，函数返回真，否则返回假。

**异常:**如果传递的参数为空，该方法将抛出*空指针异常*。

下面的程序说明了 Java.util.ArrayDeque.offerLast()方法:

**程序 1:** 将字符串元素添加到德格中。

```java
// Java code to illustrate offerLast()
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
        System.out.println("Initial Deque: " + de_que);

        // Using offerLast() to add elements
        de_que.offerLast("Hello");
        de_que.offerLast("World");

        // Displaying the ArrayDeque
        System.out.println("Final Deque: " + de_que);
    }
}
```

**Output:**

```java
Initial Deque: [Welcome, To, Geeks, 4, Geeks]
Final Deque: [Welcome, To, Geeks, 4, Geeks, Hello, World]

```

**程序 2:** 将整数元素加入到德格中。

```java
// Java code to illustrate offerLast()
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
        System.out.println("Initial Deque: " + de_que);

        // Using offerLast() to add elements
        de_que.offerLast(1658);
        de_que.offerLast(2458);

        // Displaying the ArrayDeque
        System.out.println("Final Deque: " + de_que);
    }
}
```

**Output:**

```java
Initial Deque: [10, 15, 30, 20, 5]
Final Deque: [10, 15, 30, 20, 5, 1658, 2458]

```