# Java 中的 linkedblockingrequeremovefirst()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-remove first-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-removefirst-method-in-java/)

**的 **removeFirst()** 方法链接锁定请求**返回并从中移除德奎容器的第一个元素。如果德奎容器是空的，该方法抛出一个 *NoSuchElementException* 。

**语法:**

```
public E removeFirst()
```

**返回:**该方法返回德清容器的**头**，这是第一个元素。

**异常**:如果德格为空，该函数抛出 **NoSuchElementException** 。

下面的程序说明了 link edblockingrequest 的 removeFirst()方法:

**程序 1:**

```
// Java Program to demonstrate removeFirst()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add(7855642);
        LBD.add(35658786);
        LBD.add(5278367);
        LBD.add(74381793);

        // print Dequee
        System.out.println("Linked Blocking Deque: " + LBD);

        // removes the front element and prints it
        System.out.println("First element of Linked Blocking Deque: "
                           + LBD.removeFirst());

        // prints the Deque
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]

First element of Linked Blocking Deque: 7855642

Linked Blocking Deque: [35658786, 5278367, 74381793]

```

**程序二:**

```
// Java Program to demonstrate removeFirst()
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

        // print Dequee
        System.out.println("Linked Blocking Deque: " + LBD);

        try {
            // throws an exception
            LBD.removeFirst();
        }
        catch (Exception e) {
            System.out.println("Exception when removing "
                               + "first element from this Deque: "
                               + e);
        }
    }
}
```

**输出:**

```
Linked Blocking Deque: []
Exception when removing first element from this Deque: java.util.NoSuchElementException

```