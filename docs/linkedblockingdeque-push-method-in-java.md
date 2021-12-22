# Java 中 LinkedBlockingDeque push()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-push-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-push-method-in-java/)

**的 **push(E e)** 方法将一个元素推送到这个 Deque 所代表的堆栈上。如果有空间，它会将参数中传递的元素插入到 Deque 的前面。如果链接锁定请求受到容量限制，并且没有空间可供插入，它将返回一个*非法状态异常*。这个函数类似于 addFirst()的函数。**

**语法:**

```java
public void push(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到链接锁定请求前面的元素。

**返回:**这个方法不返回任何东西。

**异常:**

*   [T0】 illegalstatexception 【T1]: If the element cannot be added due to capacity limitation at this time.
*   [T0】 NullPointerException 【T1]: If the specified element is empty.

下面的程序说明了 link edblockingrequest 的 push()方法:

**程序 1:**

```java
// Java Program Demonstrate push()
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

        // Add numbers to end of LinkedBlockingDeque
        LBD.push(7855642);
        LBD.push(35658786);
        LBD.push(5278367);
        LBD.push(74381793);

        // before removing print queue
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
// Java Program Demonstrate push()
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

        // Add numbers to end of LinkedBlockingDeque
        LBD.push(7855642);
        LBD.push(35658786);
        LBD.push(5278367);

        // it is full
        LBD.push(74381793);

        // before removing print queue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.IllegalStateException: Deque full
    at java.util.concurrent.LinkedBlockingDeque.addFirst(LinkedBlockingDeque.java:326)
    at java.util.concurrent.LinkedBlockingDeque.push(LinkedBlockingDeque.java:770)
    at GFG.main(GFG.java:23)

```

**节目 3:**

```java
// Java Program Demonstrate push()
// method of LinkedBlockingDeque
// when null is inserted

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.push(7855642);
        LBD.push(35658786);
        LBD.push(5278367);

        // NULL
        LBD.push(null);

        // before removing print queue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.NullPointerException
    at java.util.concurrent.LinkedBlockingDeque.offerFirst(LinkedBlockingDeque.java:342)
    at java.util.concurrent.LinkedBlockingDeque.addFirst(LinkedBlockingDeque.java:325)
    at java.util.concurrent.LinkedBlockingDeque.push(LinkedBlockingDeque.java:770)
    at GFG.main(GFG.java:23)

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedblockingrequest . html # push(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#push(E))