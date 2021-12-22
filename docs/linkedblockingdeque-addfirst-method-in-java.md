# Java 中的 LinkedBlockingDeque addFirst()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-addfirst-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-addfirst-method-in-java/)

**的 **addFirst(E e)** 方法 link edblockingeque**将参数中传递的元素插入到 Deque 的前面(如果有空间的话)。如果链接锁定请求受到容量限制，并且没有空间可供插入，它将返回一个*非法状态异常*。

**语法:**

```
public void addFirst(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入链接锁定请求前面的元素。

**返回:**这个方法不返回任何东西。

**异常:**

*   [T0】 illegalstatexception 【T1]: If the element cannot be added due to capacity limitation at this time.
*   [T0】 NullPointerException 【T1]: If the specified element is empty.

下面的程序说明了优先级阻塞队列的 addFirst()方法:

**程序 1:**

```
// Java Program Demonstrate addFirst()
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
    }
}
```

**输出:**

```
Linked Blocking Deque: [74381793, 5278367, 35658786, 7855642]

```

**节目 2:**

```
// Java Program Demonstrate addFirst()
// method of LinkedBlockingDeque
// when it is Full
import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of LinkedBlockingDeque
        // size of list
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>(3);

        // Add numbers to front of LinkedBlockingDeque
        LBD.addFirst(7855642);
        LBD.addFirst(35658786);
        LBD.addFirst(5278367);

        // it is full
        LBD.addFirst(74381793);

        // before removing print queue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```
Exception in thread "main" java.lang.IllegalStateException: Deque full
    at java.util.concurrent.LinkedBlockingDeque.addFirst(LinkedBlockingDeque.java:326)
    at GFG.main(GFG.java:23)

```

**节目 3:**

```
// Java Program Demonstrate addFirst()
// method of LinkedBlockingDeque
// when nill is inserted

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

        // NULL
        LBD.addFirst(null);

        // before removing print queue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```
Exception in thread "main" java.lang.NullPointerException
    at java.util.concurrent.LinkedBlockingDeque.offerFirst(LinkedBlockingDeque.java:342)
    at java.util.concurrent.LinkedBlockingDeque.addFirst(LinkedBlockingDeque.java:325)
    at GFG.main(GFG.java:22)

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedblockingrequest . html # add(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#add(E))