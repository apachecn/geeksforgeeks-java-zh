# Java 中的 ArrayDeque addFirst()方法

> 原文:[https://www . geesforgeks . org/arraydeque-addfirst-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-addfirst-method-in-java/)

java 中的 Java . util . arrayDeque . addfirst(*Object 元素*)方法用于在这个 deque 的前面插入一个特定的元素。

**语法:**

```
Array_Deque.addFirst(*Object element*)
```

**参数:**参数*元素*属于数组类型，指的是要添加的元素。

**返回值:**函数不返回值。

**异常:**如果传递的参数为空，该方法将抛出*空指针异常*。

下面的程序说明了 Java.util.ArrayDeque.addFirst()方法:
**程序 1:**

```
// Java code to illustrate addFirst()
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

        // Adding elements at front
        de_que.addFirst(40);
        de_que.addFirst(50);
        de_que.addFirst(60);
        de_que.addFirst(70);

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque_front_addition: " + de_que);

        // Adding elements using add()
        de_que.add(1);
        de_que.add(2);
        de_que.add(3);

        // Displaying the final ArrayDeque
        System.out.println("Final ArrayDeque: " + de_que);
    }
}
```

**Output:**

```
ArrayDeque: [10, 15, 30, 20, 5]
ArrayDeque_front_addition: [70, 60, 50, 40, 10, 15, 30, 20, 5]
Final ArrayDeque: [70, 60, 50, 40, 10, 15, 30, 20, 5, 1, 2, 3]

```

**程序 2:**

```
// Java code to illustrate addFirst()
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

        // Adding elements at front
        de_que.addFirst("GFG");
        de_que.addFirst("World");
        de_que.addFirst("Hello");

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque_front_addition: " + de_que);

        // Adding elements using add()
        de_que.add("Coding");
        de_que.add("At");
        de_que.add("BEST");

        // Displaying the final ArrayDeque
        System.out.println("Final ArrayDeque: " + de_que);
    }
}
```

**Output:**

```
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
ArrayDeque_front_addition: [Hello, World, GFG, Welcome, To, Geeks, 4, Geeks]
Final ArrayDeque: [Hello, World, GFG, Welcome, To, Geeks, 4, Geeks, Coding, At, BEST]

```