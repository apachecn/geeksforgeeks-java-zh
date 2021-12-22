# Java 中的 ArrayDeque addLast()方法

> 原文:[https://www . geesforgeks . org/arraydeque-addlast-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-addlast-method-in-java/)

java 中的 Java . util . arrayDeque . addlast(*Object 元素*)方法是用来在这个 deque 的末尾插入一个特定的元素。它类似于 Java 中的 add()方法。

**语法:**

```
Array_Deque.addLast(*Object element*)
```

**参数:**参数*元素*属于数组类型，指的是要添加的元素。

**返回值:**函数不返回值。

**异常:**如果传递的参数为空，该方法将抛出*空指针异常*。

下面的程序说明了 Java.util.ArrayDeque.addLast()方法:
**程序 1:** 将整数加到 Deque。

```
// Java code to illustrate addLast()
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

        // Adding elements at the end
        de_que.addLast(40);
        de_que.addLast(50);
        de_que.addLast(60);
        de_que.addLast(70);

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque_end_addition: " + de_que);
    }
}
```

**Output:**

```
ArrayDeque: [10, 15, 30, 20, 5]
ArrayDeque_end_addition: [10, 15, 30, 20, 5, 40, 50, 60, 70]

```

**程序 2:** 将字符串添加到德格。

```
// Java code to illustrate addLast()
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

        // Adding elements at end
        de_que.addLast("GFG");
        de_que.addLast("World");
        de_que.addLast("Hello");

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque_end_addition: " + de_que);
    }
}
```

**Output:**

```
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
ArrayDeque_end_addition: [Welcome, To, Geeks, 4, Geeks, GFG, World, Hello]

```