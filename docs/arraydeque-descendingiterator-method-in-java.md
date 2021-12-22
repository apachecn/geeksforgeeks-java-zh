# Java 中的 ArrayDeque 下行 terator()方法

> 原文:[https://www . geeksforgeeks . org/arraydeque-dependingiterator-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-descendingiterator-method-in-java/)

Java . util . ArrayDeque . DecendingTerrar()方法用于返回与 ArrayDeque 元素相同但顺序相反的迭代器。

**语法:**

```
Iterator iterate_value = Array_Deque.descendingIterator();
```

**参数:**该方法不取任何参数。

**返回值:**该方法迭代 deque 的元素，并以相反的顺序返回值(迭代器)。

下面的程序举例说明了 Java . util . arraydeque . decending terator()方法:
**程序 1:**

```
// Java code to illustrate descendingIterator()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<String> de_que = new ArrayDeque<String>();

        // Use add() method to add elements into the Queue
        de_que.add("Welcome");
        de_que.add("To");
        de_que.add("Geeks");
        de_que.add("4");
        de_que.add("Geeks");

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);

        // Creating a desc_iterator
        Iterator value = de_que.descendingIterator();

        // Displaying the values after iterating through the Deque
        // in reverse order
        System.out.println("The iterator values are: ");
        while (value.hasNext()) {
            System.out.println(value.next());
        }
    }
}
```

**Output:**

```
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
The iterator values are: 
Geeks
4
Geeks
To
Welcome

```

**程序 2:**

```
// Java code to illustrate descendingIterator()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<Integer> de_que = new ArrayDeque<Integer>();

        // Use add() method to add elements into the Queue
        de_que.add(10);
        de_que.add(15);
        de_que.add(30);
        de_que.add(20);
        de_que.add(5);

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);

        // Creating a desc_iterator
        Iterator value = de_que.descendingIterator();

        // Displaying the values after iterating through the Deque
        // in reverse order
        System.out.println("The iterator values are: ");
        while (value.hasNext()) {
            System.out.println(value.next());
        }
    }
}
```

**Output:**

```
ArrayDeque: [10, 15, 30, 20, 5]
The iterator values are: 
5
20
30
15
10

```