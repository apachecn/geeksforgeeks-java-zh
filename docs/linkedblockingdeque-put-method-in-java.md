# Java 中 LinkedBlockingDeque put()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingrequest-put-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-put-method-in-java/)

**的 **put(E e)** 方法链接锁定队列**将指定的元素插入到这个队列所代表的队列中(换句话说，在这个队列的尾部)。如果德奎是容量受限的，那么它将等待空间变得可用。

**语法:**

```java
public void put(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到链接锁定请求末尾的元素。

**返回:**此方法不返回任何内容。

**异常:**程序抛出如下所示的两个异常:

*   **null pointerexception** -If the specified element is empty
*   **Interrupt exception** –If you interrupt while waiting

下面的程序说明了 link edblockingrequest 的 put()方法:

**程序 1:**

```java
// Java Program Demonstrate put()
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
        LBD.put(7855642);
        LBD.put(35658786);
        LBD.put(5278367);
        LBD.put(74381793);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```java
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]

```

**节目 2:**

```java
// Java Program Demonstrate put()
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
        LBD.put(7855642);
        LBD.put(35658786);
        LBD.put(5278367);

        // throws an exception
        LBD.put(null);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出** :

```java
Exception in thread "main" java.lang.NullPointerException
    at java.util.concurrent.LinkedBlockingDeque.putLast(LinkedBlockingDeque.java:390)
    at java.util.concurrent.LinkedBlockingDeque.put(LinkedBlockingDeque.java:649)
    at GFG.main(GFG.java:22)

```

**节目 3:**

```java
// Java Program Demonstrate put()
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
        LBD.put(7855642);
        LBD.put(35658786);
        LBD.put(5278367);

        // throws an exception
        LBD.put(4356789);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出** :

```java
Runtime Errors:
Max real time limit exceeded due to either by heavy load on server or by using sleep function

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingrequest . html # put-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#put-E-)