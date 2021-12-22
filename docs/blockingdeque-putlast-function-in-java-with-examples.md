# Java 中 BlockingDeque putLast()函数示例

> 原文:[https://www . geeksforgeeks . org/blockingrequest-putlast-function-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-putlast-function-in-java-with-examples/)

**阻塞请求**的 **putLast(E e)** 方法将指定的元素插入到这个队列所代表的队列中(换句话说，在这个队列的尾部/末端)。如果德奎是容量受限的，那么它将等待空间变得可用。

**语法:**

```java
public void putLast(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到阻塞请求末尾的元素。

**返回:**此方法不返回任何内容。

**异常:**程序抛出如下所示的两个异常:

*   **null pointerexception** -If the specified element is empty
*   **Interrupt exception** –If you interrupt while waiting

**注**:**blocking eque**的 putLast()方法继承自 Java 中的[link edblocking eque](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类。

下面的程序说明了 putLast()方法的阻塞请求:

**程序 1:**

```java
// Java Program Demonstrate putLast()
// method of BlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.putLast(7855642);
        BD.putLast(35658786);
        BD.putLast(5278367);
        BD.putLast(74381793);

        // print Dequeue
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
// Java Program Demonstrate putLast()
// method of BlockingDeque
// throwing NullPointerException

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.putLast(7855642);
        BD.putLast(35658786);
        BD.putLast(5278367);

        // throws an exception
        BD.putLast(null);

        // print Dequeue
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出** :

```java
Exception in thread "main" java.lang.NullPointerException
    at java.util.concurrent.LinkedBlockingDeque.putLast(LinkedBlockingDeque.java:390)
    at GFG.main(GFG.java:24)

```

**节目 3:**

```java
// Java Program Demonstrate putLast()
// method of BlockingDeque
// when capacity exceeded

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>(3);

        // Add numbers to end of BlockingDeque
        BD.putLast(7855642);
        BD.putLast(35658786);
        BD.putLast(5278367);

        // throws an exception
        BD.putLast(4356789);

        // print Dequeue
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出** :

```java
Max real time limit exceeded due to either by heavy load on server or by using sleep function

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blockingdequee . html # putLast(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#putLast(E))