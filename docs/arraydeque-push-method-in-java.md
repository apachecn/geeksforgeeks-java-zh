# Java 中的 ArrayDeque push()方法

> 原文:[https://www . geesforgeks . org/arraydeque-push-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-push-method-in-java/)

Java.util.ArrayDeque.push(E 元素)方法用于将一个元素推入到 Deque 中。该操作类似于堆栈中的操作。该元素被推送到 deque 的顶部。

**语法:**

```
Array_Deque.push(*E element*)
```

**参数:**参数*元素*的类型为 ArrayDeque，指的是要推入 Deque 的元素。

**返回值:**该方法不返回值。

**异常:**如果传递的参数为空，该方法将抛出*空指针异常*。

下面的程序说明了 Java.util.ArrayDeque.push()方法:
**程序 1:** 将字符串元素添加到 Deque 中。

```
// Java code to illustrate push()
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

        // Displaying the initial ArrayDeque
        System.out.println("Initial Deque: " + de_que);

        // Pushing elements into the deque
        de_que.push("Hello");
        de_que.push("World");

        // Displaying the final ArrayDeque
        System.out.println("Final Deque: " + de_que);
    }
}
```

**Output:**

```
Initial Deque: [Welcome, To, Geeks, 4, Geeks]
Final Deque: [World, Hello, Welcome, To, Geeks, 4, Geeks]

```

**程序 2:** 将整数元素加入到德格中。

```
// Java code to illustrate push()
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

        // Displaying the initial ArrayDeque
        System.out.println("Initial Deque: " + de_que);

        // Pushing elements into the deque
        de_que.push(1254);
        de_que.push(4521);

        // Displaying the final ArrayDeque
        System.out.println("Final Deque: " + de_que);
    }
}
```

**Output:**

```
Initial Deque: [10, 15, 30, 20, 5]
Final Deque: [4521, 1254, 10, 15, 30, 20, 5]

```