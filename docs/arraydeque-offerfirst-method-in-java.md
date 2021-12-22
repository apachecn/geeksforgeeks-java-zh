# Java 中的 ArrayDeque offerFirst()方法

> 原文:[https://www . geeksforgeeks . org/arraydeque-offer first-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-offerfirst-method-in-java/)

Java 中的 Java . util . arraydeque . offer first(*Object 元素*)方法用于在 Deque 的前面添加一个特定的元素。该函数类似于 Java 中 ArrayDeque 的 [addFirst()](https://www.geeksforgeeks.org/arraydeque-addfirst-method-in-java/) 方法。

**语法:**

```
Array_Deque.offerFirst(*Object element*)
```

**参数:**参数*元素*为 ArrayDeque 类型，指的是要添加到德格前面的元素。

**返回值:**如果元素被成功添加到 deque 中，函数返回真，否则返回假。

**异常:**如果传递的参数为空，该方法将抛出*空指针异常*。

下面的程序说明了 Java . util . arraydeque . offer first()方法:
**程序 1:** 将字符串元素添加到 Deque 中。

```
// Java code to illustrate offerFirst()
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

        // Using offerFirst() to add elements
        de_que.offerFirst("World");
        de_que.offerFirst("Hello");

        // Displaying the ArrayDeque
        System.out.println("Final Deque: " + de_que);
    }
}
```

**Output:**

```
Initial Deque: [Welcome, To, Geeks, 4, Geeks]
Final Deque: [Hello, World, Welcome, To, Geeks, 4, Geeks]

```

**程序 2:** 将整数元素加入到德格中。

```
// Java code to illustrate offerFirst()
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

        // Using offerFirst() to add elements
        de_que.offerFirst(1658);
        de_que.offerFirst(2458);

        // Displaying the ArrayDeque
        System.out.println("Final Deque: " + de_que);
    }
}
```

**Output:**

```
Initial Deque: [10, 15, 30, 20, 5]
Final Deque: [2458, 1658, 10, 15, 30, 20, 5]

```