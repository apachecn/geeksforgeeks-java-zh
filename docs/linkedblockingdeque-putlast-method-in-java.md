# Java 中 linkedblockingrequeputlast()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-putlast-in-method-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-putlast-method-in-java/)

**的 **putLast(E e)** 方法将指定的元素插入到这个队列所代表的队列中(换句话说，在这个队列的尾部/末端)。如果德奎是容量受限的，那么它将等待空间变得可用。**

**语法:**

```
public void putLast(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到链接锁定请求末尾的元素。

**返回:**此方法不返回任何内容。

**异常:**程序抛出如下所示的两个异常:

*   **null pointerexception** -If the specified element is empty
*   **Interrupt exception** –If you interrupt while waiting

下面的程序说明了链接锁定请求的 putLast()方法:

**程序 1:**

```
// Java Program Demonstrate putLast()
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
        LBD.putLast(7855642);
        LBD.putLast(35658786);
        LBD.putLast(5278367);
        LBD.putLast(74381793);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]

```

**节目 2:**

```
// Java Program Demonstrate putLast()
// method of LinkedBlockingDeque
// throwing NullPointerException

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
        LBD.putLast(7855642);
        LBD.putLast(35658786);
        LBD.putLast(5278367);

        // throws an exception
        LBD.putLast(null);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出** :

```
Runtime Errors:
Exception in thread "main" java.lang.NullPointerException
    at java.util.concurrent.LinkedBlockingDeque.putLast(LinkedBlockingDeque.java:390)
    at GFG.main(GFG.java:23)

```

**节目 3:**

```
// Java Program Demonstrate putLast()
// method of LinkedBlockingDeque
// when capacity exceeded

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>(3);

        // Add numbers to end of LinkedBlockingDeque
        LBD.putLast(7855642);
        LBD.putLast(35658786);
        LBD.putLast(5278367);

        // throws an exception
        LBD.putLast(4356789);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出** :

```
Runtime Errors:
Max real time limit exceeded due to either by heavy 
load on server or by using sleep function

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingrequest . html # putLast-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#putLast-E-)