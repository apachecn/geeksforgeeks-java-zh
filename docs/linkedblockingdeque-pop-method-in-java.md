# Java 中 link edblockingdevelop()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-pop-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-pop-method-in-java/)

**的 **pop()** 方法链接锁定命令**从该命令所代表的堆栈中弹出一个元素。换句话说，它移除并返回这个 deque 的第一个元素。如果容器是空的，它将返回**空值**。

**语法:**

```java
public E pop()
```

**参数:**此方法不接受任何参数。

**返回:**这个方法返回这个得克前面的元素(*是这个得克所代表的栈顶*)。如果德格是空的，它会抛出一个*T5【NoSuchElementException*。

下面的程序说明了链接锁定请求的 pop()方法:

**程序 1:**

```java
// Java Program to demonstrate pop()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws NoSuchElementException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.addFirst(7855642);
        LBD.addFirst(35658786);
        LBD.addFirst(5278367);
        LBD.addFirst(74381793);

        // Print the queue
        System.out.println("Linked Blocking Deque: " + LBD);

        // prints and deletes
        System.out.println("Front element in Deque: " + LBD.pop());

        // Deque after deletion of front element
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```java
Linked Blocking Deque: [74381793, 5278367, 35658786, 7855642]
Front element in Deque: 74381793
Linked Blocking Deque: [5278367, 35658786, 7855642]

```

**节目 2:**

```java
// Java Program Demonstrate pop()
// method of LinkedBlockingDeque
// when Deque is empty

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)

    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add(7855642);
        LBD.add(35658786);
        LBD.add(5278367);
        LBD.add(74381793);

        // empty deque
        LBD.clear();

        System.out.println("Front element in Deque: " + LBD.pop());
    }
}
```

**输出:**

```java
Exception in thread "main" java.util.NoSuchElementException
    at java.util.concurrent.LinkedBlockingDeque.removeFirst(LinkedBlockingDeque.java:453)
    at java.util.concurrent.LinkedBlockingDeque.pop(LinkedBlockingDeque.java:777)
    at GFG.main(GFG.java:27)
```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedblockingrequest . html # pop()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#pop())