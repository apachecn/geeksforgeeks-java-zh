# Java 中的 linkedblockingrequeaddlast()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-addlast-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-addlast-method-in-java/)

**的 **addLast(E e)** 方法链接锁定命令**将参数中传递的元素插入到目标的末尾(如果有空间的话)。如果链接锁定请求受到容量限制，并且没有空间可供插入，它将返回一个*非法状态异常*。

**语法:**

```java
public void addLast(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到链接锁定请求末尾的元素。

**返回:**这个方法不返回任何东西。

**异常:**

*   [T0】 illegalstatexception 【T1]: If the element cannot be added due to capacity limitation at this time.
*   [T0】 NullPointerException 【T1]: If the specified element is empty.

下面的程序说明了 link edblockingrequest 的 addLast()方法:

**程序 1:**

```java
// Java Program Demonstrate addLast()
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
        LBD.addLast(7855642);
        LBD.addLast(35658786);
        LBD.addLast(5278367);
        LBD.addLast(74381793);

        // before removing print queue
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
// Java Program Demonstrate addLast()
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
        LBD.addLast(7855642);
        LBD.addLast(35658786);
        LBD.addLast(5278367);

        // it is full
        LBD.addLast(74381793);

        // before removing print queue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.IllegalStateException: Deque full
    at java.util.concurrent.LinkedBlockingDeque.addLast(LinkedBlockingDeque.java:335)
    at GFG.main(GFG.java:23)

```

**节目 3:**

```java
// Java Program Demonstrate addLast()
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

        // Add numbers to end of LinkedBlockingDeque
        LBD.addLast(7855642);
        LBD.addLast(35658786);
        LBD.addLast(5278367);

        // NULL
        LBD.addLast(null);

        // before removing print queue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.NullPointerException
    at java.util.concurrent.LinkedBlockingDeque.offerLast(LinkedBlockingDeque.java:357)
    at java.util.concurrent.LinkedBlockingDeque.addLast(LinkedBlockingDeque.java:334)
    at GFG.main(GFG.java:23)

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedblockingrequest . html # addLast(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#addLast(E))