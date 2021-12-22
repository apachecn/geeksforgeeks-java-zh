# Java 中 LinkedBlockingDeque putFirst()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-put first-in-method-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-putfirst-method-in-java/)

**的 **putFirst(E e)** 方法链接锁定队列**将指定的元素插入到这个队列所代表的队列的前面。如果德奎是容量受限的，那么它将等待空间变得可用。

**语法:**

```java
public void putFirst(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到链接锁定请求前面的元素。

**返回:**此方法不返回任何内容。

**异常:**程序抛出如下所示的两个异常:

*   **null pointerexception** -If the specified element is empty
*   **Interrupt exception** –If you interrupt while waiting

下面的程序说明了链接锁定请求的 putFirst()方法:

**程序 1:**

```java
// Java Program Demonstrate putFirst()
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
        LBD.putFirst(7855642);
        LBD.putFirst(35658786);
        LBD.putFirst(5278367);
        LBD.putFirst(74381793);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```java
Linked Blocking Deque: [74381793, 5278367, 35658786, 7855642]

```

**节目 2:**

```java
// Java Program Demonstrate putFirst()
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
        LBD.putFirst(7855642);
        LBD.putFirst(35658786);
        LBD.putFirst(5278367);

        // throws an exception
        LBD.putFirst(null);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出** :

```java
Exception in thread "main" java.lang.NullPointerException
    at java.util.concurrent.LinkedBlockingDeque.putFirst(LinkedBlockingDeque.java:373)
    at GFG.main(GFG.java:23)

```

**节目 3:**

```java
// Java Program Demonstrate putFirst()
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
        LBD.putFirst(7855642);
        LBD.putFirst(35658786);
        LBD.putFirst(5278367);

        // throws an exception
        LBD.putFirst(4356789);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出** :

```java
Runtime Errors:
Max real time limit exceeded due to either by
heavy load on server or by using sleep function

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingrequest . html # putFirst-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#putFirst-E-)