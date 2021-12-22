# Java 中的 BlockingDeque addLast()方法，示例

> 原文:[https://www . geeksforgeeks . org/blocking reque-addlast-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-addlast-method-in-java-with-examples/)

**的 **addLast(E e)** 方法 blocking eque**将参数中传递的元素插入到 Deque 的末尾(如果有空间的话)。如果阻塞请求受到容量限制并且没有空间可供插入，它将返回一个*非法状态异常*。

**语法:**

```
public void addLast(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到阻塞请求末尾的元素。

**返回:**这个方法不返回任何东西。

**异常:**

*   [T0】 illegalstatexception 【T1]: If the element cannot be added due to capacity limitation at this time.
*   [T0】 NullPointerException 【T1]: If the specified element is empty.

**注**:**blocking eque**的 addLast()方法继承自 Java 中的[link edblocking eque](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类。

下面的程序说明了阻止请求的 addLast()方法:

**程序 1:**

```
// Java Program Demonstrate addLast()
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
        BD.addLast(7855642);
        BD.addLast(35658786);
        BD.addLast(5278367);
        BD.addLast(74381793);

        // before removing print Deque
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```
Blocking Deque: [7855642, 35658786, 5278367, 74381793]

```

**节目 2:**

```
// Java Program Demonstrate addLast()
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
        BD.addLast(7855642);
        BD.addLast(35658786);
        BD.addLast(5278367);

        // it is full
        BD.addLast(74381793);

        // before removing print Deque
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```
Exception in thread "main" java.lang.IllegalStateException: Deque full
    at java.util.concurrent.LinkedBlockingDeque.addLast(LinkedBlockingDeque.java:335)
    at GFG.main(GFG.java:25)

```

**节目 3:**

```
// Java Program Demonstrate addLast()
// method of BlockingDeque
// when nill is inserted

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
        BD.addLast(7855642);
        BD.addLast(35658786);
        BD.addLast(5278367);

        // NULL
        BD.addLast(null);

        // before removing print queue
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```
Exception in thread "main" java.lang.NullPointerException
    at java.util.concurrent.LinkedBlockingDeque.offerLast(LinkedBlockingDeque.java:357)
    at java.util.concurrent.LinkedBlockingDeque.addLast(LinkedBlockingDeque.java:334)
    at GFG.main(GFG.java:24)

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blocking request . html # addLast(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#addLast(E))