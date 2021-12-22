# Java 中的 linkedblockingrequegetlast()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingreque-get last-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-getlast-method-in-java/)

**的 **getLast()** 方法链接了锁定请求**返回了德奎容器中的最后一个元素。如果 LinkedBlockingDeque 为空，那么在函数调用时，它会返回一个 *NoSuchElementException* 。

**语法:**

```
public E getLast()
```

**参数:**此方法不接受任何参数。

**返回:**这个方法返回这个 Deque 容器的最后一个元素。

**异常:**该函数在 deque 为空时只抛出一个异常，即***no suchelementexception***

下面的程序说明了 linkedblockingrequest 的 getLast()方法:

**程序 1:**

```
// Java Program Demonstrate getLast()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to front of LinkedBlockingDeque
        LBD.addFirst(7855642);
        LBD.addFirst(35658786);
        LBD.addFirst(5278367);
        LBD.addFirst(74381793);

        // before removing print queue
        System.out.println("Linked Blocking Deque: " + LBD);

        // prints the last element
        System.out.println("Linked Blocking Deque first element: " +
                                                     LBD.getLast());
    }
}
```

**输出:**

```
Linked Blocking Deque: [74381793, 5278367, 35658786, 7855642]
Linked Blocking Deque first element: 7855642

```

**节目 2:**

```
// Java Program Demonstrate getLast()
// method of LinkedBlockingDeque
// shows exception

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to front of LinkedBlockingDeque
        LBD.addFirst(7855642);
        LBD.addFirst(35658786);
        LBD.addFirst(5278367);
        LBD.addFirst(74381793)

            LBD.clear();

        // Since the container is empty it will throw exception
        System.out.println("Linked Blocking Deque first element: " + 
                                                     LBD.getLast());
    }
}
```

**输出:**

```
Exception in thread "main" java.util.NoSuchElementException
    at java.util.concurrent.LinkedBlockingDeque.getLast(LinkedBlockingDeque.java:553)
    at GFG.main(GFG.java:28)

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedblockingrequest . html # getLast()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#getLast())