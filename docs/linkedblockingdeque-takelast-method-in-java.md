# Java 中 linkedblockingdequetaklast()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-take last-in-method-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-takelast-method-in-java/)

**的 **takeLast()** 方法链接锁定请求**返回并移除德格容器的尾部。如果在等待时被中断，该方法将抛出*中断异常*。

**语法:**

```
public E takeLast()
```

**返回:**该方法返回德雀容器的**尾(最后一个元素)**。

**异常**:如果在等待时被中断，该功能会抛出*中断异常*。

下面的程序说明了 *takeLast()* 链接锁定请求的方法:

**节目 1:**

```
// Java Program to demonstrate takeLast()
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

        // removes the last element and prints it
        System.out.println("Head of Linked Blocking Deque: "
                           + LBD.takeLast());

        // prints the Deque
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Head of Linked Blocking Deque: 74381793
Linked Blocking Deque: [7855642, 35658786, 5278367]

```

**节目 2:**

```
// Java Program to demonstrate takeLast()
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

        LBD.clear();

        // throws error as the list is empty and it
        // is interrupted while waiting
        System.out.println("Head of Linked Blocking Deque: "
                           + LBD.takeLast());
    }
}
```

**运行时错误:**

```
Max real time limit exceeded due to either by heavy load on server or by using sleep function

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingrequest . html # take last–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#takeLast--)