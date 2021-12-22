# Java 中 linkedblockingrequesize()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-size-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-size-method-in-java/)

**的 **size()** 方法链接了锁定请求**返回当前的德格容器大小。在调用该函数时，将返回 Deque 容器中的元素数量。如果容器是容量受限的，那么它还返回在函数调用时容器中存在的元素的数量。

**语法:**

```
public int size()
```

**返回:**该方法返回一个**整数**值，表示容器中的元素数量。

下面的程序说明了 linkedblockingrequest 的 size()方法:

**程序 1:**

```
// Java Program to demonstrate public int size()
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
        LBD.add(15);
        LBD.add(20);
        LBD.add(20);
        LBD.add(15);
        LBD.add(15);
        LBD.add(20);
        LBD.add(20);
        LBD.add(15);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);

        // prints the Deque after removal
        System.out.println("Size of Linked Blocking Deque: "
                           + LBD.size());
    }
}
```

**输出:**

```
Linked Blocking Deque: [15, 20, 20, 15, 15, 20, 20, 15]
Size of Linked Blocking Deque: 8

```

**程序二:**

```
// Java Program to demonstrate public int size()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<String> LBD
            = new LinkedBlockingDeque<String>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add("geeks");
        LBD.add("forGeeks");
        LBD.add("A Computer");
        LBD.add("Portal");

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);

        // prints the Deque after removal
        System.out.println("Size of Linked Blocking Deque: "
                           + LBD.size());
    }
}
```

**输出:**

```
Linked Blocking Deque: [geeks, forGeeks, A Computer, Portal]
Size of Linked Blocking Deque: 4

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingrequest . html # size–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#size--)