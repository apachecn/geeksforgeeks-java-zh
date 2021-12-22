# Java 中的 BlockingDeque add()方法，示例

> 原文:[https://www . geeksforgeeks . org/blocking reque-add-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-add-method-in-java-with-examples/)

**的 **add(E e)** 方法 blocking eque**将参数中传递的元素插入到有空格的 Deque 的末尾。如果阻塞请求受到容量限制并且没有空间可供插入，它将返回一个*非法状态异常*。它的工作方式与 addLast()方法完全相同。

**语法:**

```java
public void add(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到阻塞请求末尾的元素。

**返回:**这个方法不返回任何东西。

**异常:**

*   [T0】 illegalstatexception 【T1]: If the element cannot be added due to capacity limitation at this time.
*   [T0】 NullPointerException 【T1]: If the specified element is empty.

**注**:**blocking eque**的 add()方法继承了 Java 中的[link edblocking eque](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类。

下面的程序说明了添加()的方法:

**程序 1:**

```java
// Java Program Demonstrate add()
// method of BlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.add(7855642);
        BD.add(35658786);
        BD.add(5278367);
        BD.add(74381793);

        // before removing print queue
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```java
Blocking Deque: [7855642, 35658786, 5278367, 74381793]

```

**节目 2:**

```java
// Java Program Demonstrate add()
// method of BlockingDeque
// when it is Full
import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingDeque
        // size of list
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>(3);

        // Add numbers to end of BlockingDeque
        BD.add(7855642);
        BD.add(35658786);
        BD.add(5278367);

        // it is full
        BD.add(74381793);

        // before removing print Deque
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.IllegalStateException: Deque full
    at java.util.concurrent.LinkedBlockingDeque.addLast(LinkedBlockingDeque.java:335)
    at java.util.concurrent.LinkedBlockingDeque.add(LinkedBlockingDeque.java:633)
    at GFG.main(GFG.java:24)

```

**节目 3:**

```java
// Java Program Demonstrate add()
// method of BlockingDeque
// when null is inserted

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.add(7855642);
        BD.add(35658786);
        BD.add(5278367);

        // NULL
        BD.add(null);

        // before removing print Deque
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.NullPointerException
    at java.util.concurrent.LinkedBlockingDeque.offerLast(LinkedBlockingDeque.java:357)
    at java.util.concurrent.LinkedBlockingDeque.addLast(LinkedBlockingDeque.java:334)
    at java.util.concurrent.LinkedBlockingDeque.add(LinkedBlockingDeque.java:633)
    at GFG.main(GFG.java:23)

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blockingdequee . html # add(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#add(E))