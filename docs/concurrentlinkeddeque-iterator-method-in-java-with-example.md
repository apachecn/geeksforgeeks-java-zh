# Java 中的 concurrentlinkedequeiterator()方法，示例

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-iterator-method-in-Java-with-example/](https://www.geeksforgeeks.org/concurrentlinkeddeque-iterator-method-in-java-with-example/)

**Java . util . concurrentlinkedrequest . iterator()**方法用于返回一个与 concurrentlinkedrequest 元素相同的迭代器。元素以随机顺序从 deque 中返回。

**语法:**

```
Iterator *iterate_value* = ConcurrentLinkedDeque.iterator();

```

**参数:**函数不取任何参数。

**返回值:**该方法迭代 deque 的元素并返回值(迭代器)。

下面的程序说明了 Java . util . concurrentlinkedequest . iterator()方法的使用:

**例 1:**

```
// Java code to illustrate iterator()

import java.util.concurrent.*;
import java.util.*;

public class ConcurrentLinkedDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ConcurrentLinkedDeque
        ConcurrentLinkedDeque<String> deque
            = new ConcurrentLinkedDeque<String>();

        // Use add() method to add elements
        // into the ConcurrentLinkedDeque
        deque.add("Welcome");
        deque.add("To");
        deque.add("Geeks");
        deque.add("4");
        deque.add("Geeks");

        // Displaying the ConcurrentLinkedDeque
        System.out.println("ConcurrentLinkedDeque: "
                           + deque);

        // Creating an iterator
        Iterator value = deque.iterator();

        // Displaying the values
        // after iterating through the deque
        System.out.println("The iterator values are: ");
        while (value.hasNext()) {
            System.out.println(value.next());
        }
    }
}
```

**Output:**

```
ConcurrentLinkedDeque: [Welcome, To, Geeks, 4, Geeks]
The iterator values are: 
Welcome
To
Geeks
4
Geeks

```

**示例 2:** 带有整数元素的 ConcurrentLinkedDeque。

```
// Java code to illustrate iterator()

import java.util.concurrent.*;
import java.util.*;

public class ConcurrentLinkedDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ConcurrentLinkedDeque
        ConcurrentLinkedDeque<Integer> deque
            = new ConcurrentLinkedDeque<Integer>();

        // Use add() method
        // to add elements into the ConcurrentLinkedDeque
        deque.add(10);
        deque.add(20);
        deque.add(30);
        deque.add(40);
        deque.add(50);

        // Displaying the ConcurrentLinkedDeque
        System.out.println("ConcurrentLinkedDeque: "
                           + deque);

        // Creating an iterator
        Iterator value = deque.iterator();

        // Displaying the values
        // after iterating through the deque
        System.out.println("The iterator values are: ");
        while (value.hasNext()) {
            System.out.println(value.next());
        }
    }
}
```

**Output:**

```
ConcurrentLinkedDeque: [10, 20, 30, 40, 50]
The iterator values are: 
10
20
30
40
50

```