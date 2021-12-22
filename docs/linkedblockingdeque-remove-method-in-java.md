# Java 中的 LinkedBlockingDeque remove()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-remove-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-remove-method-in-java/)

**移除()**方法**链接锁定命令**移除德克尔容器的头部。如果德奎容器是空的，该方法抛出一个 *NoSuchElementException* 。

**语法:**

```java
public E remove()
```

**参数:**该方法不接受任何参数。

**返回:**这个方法不返回任何东西。

**异常**:如果德格为空，函数抛出 *NoSuchElementException* 。

下面的程序说明了 link edblockingrequest 的 remove()方法:

**程序 1:**

```java
// Java Program Demonstrate remove()
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

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);

        // removes the front element
        LBD.remove();
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```java
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Linked Blocking Deque: [35658786, 5278367, 74381793]

```

**节目 2:**

```java
// Java Program Demonstrate remove()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws NoSuchElementException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>(6);

        // Add numbers to end of LinkedBlockingDeque
        LBD.add(7855642);
        LBD.add(35658786);
        LBD.add(5278367);
        LBD.add(74381793);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);

        // Deque is empty
        LBD.clear();

        // throws an exception
        LBD.remove();
    }
}
```

**输出:**

```java
Exception in thread "main" java.util.NoSuchElementException
    at java.util.concurrent.LinkedBlockingDeque.removeFirst(LinkedBlockingDeque.java:453)
    at java.util.concurrent.LinkedBlockingDeque.remove(LinkedBlockingDeque.java:672)
    at GFG.main(GFG.java:30)

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingrequest . html # remove–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#remove--)