# Java 中的 BlockingDeque addFirst()方法，示例

> 原文:[https://www . geeksforgeeks . org/blocking eque-addfirst-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-addfirst-method-in-java-with-examples/)

**阻塞请求**的 **addFirst(E e)** 方法将参数中传递的元素插入到有空间的德格前面。如果阻塞请求受到容量限制并且没有空间可供插入，它将返回一个*非法状态异常*。

**语法:**

```java
public void addFirst(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到阻塞请求前面的元素。

**返回:**这个方法不返回任何东西。

**异常:**

*   [T0】 illegalstatexception 【T1]: If the element cannot be added due to capacity limitation at this time.
*   [T0】 NullPointerException 【T1]: If the specified element is empty.

**注**:**blocking eque**的 addFirst()方法是从 Java 中的[link edblocking eque](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类继承而来的。

下面的程序说明了阻塞队列的 addFirst()方法:

**程序 1:**

```java
// Java Program Demonstrate addFirst()
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

        // Add numbers to front of BlockingDeque
        BD.addFirst(7855642);
        BD.addFirst(35658786);
        BD.addFirst(5278367);
        BD.addFirst(74381793);

        // before removing print Dequq
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```java
Blocking Deque: [74381793, 5278367, 35658786, 7855642]

```

**节目 2:**

```java
// Java Program Demonstrate addFirst()
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

        // Add numbers to front of BlockingDeque
        BD.addFirst(7855642);
        BD.addFirst(35658786);
        BD.addFirst(5278367);

        // it is full
        BD.addFirst(74381793);

        // before removing print Deque
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.IllegalStateException: Deque full
    at java.util.concurrent.LinkedBlockingDeque.addFirst(LinkedBlockingDeque.java:326)
    at GFG.main(GFG.java:24)

```

**节目 3:**

```java
// Java Program Demonstrate addFirst()
// method of BlockingDeque
// when nill is inserted

import java.util.concurrent.BlockingDeque;
import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to front of BlockingDeque
        BD.addFirst(7855642);
        BD.addFirst(35658786);
        BD.addFirst(5278367);

        // NULL
        BD.addFirst(null);

        // before removing print Deque
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.NullPointerException
    at java.util.concurrent.LinkedBlockingDeque.offerFirst(LinkedBlockingDeque.java:342)
    at java.util.concurrent.LinkedBlockingDeque.addFirst(LinkedBlockingDeque.java:325)
    at GFG.main(GFG.java:24)

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blocking request . html # addFirst(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#addFirst(E))