# Java 中 BlockingDeque take()方法示例

> 原文:[https://www . geeksforgeeks . org/blocking request-take-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-take-method-in-java-with-examples/)

**封锁请求**的 **take()** 方法返回并移除德格集装箱的头部。如果在等待时被中断，该方法将抛出*中断异常*。

**语法:**

```
public E take()
```

**返回:**该方法返回德格容器的头部。

**异常**:如果在等待时被中断，该功能会抛出*中断异常*。

**注**:**blocking request**的 **take()** 方法继承自 Java 中的 LinkedBlockingDeque 类。

下面程序举例说明采取()方法的阻塞请求:

**节目 1:**

```
// Java Program to demonstrate take()
// method of LinkedBlockingDeque

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
        BD.add(7855642);
        BD.add(35658786);
        BD.add(5278367);
        BD.add(74381793);

        // print Deque
        System.out.println("Blocking Deque: " + BD);

        // removes the front element and prints it
        System.out.println("Head of Blocking Deque: "
                           + BD.take());

        // prints the Deque
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```
Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Head of Blocking Deque: 7855642
Blocking Deque: [35658786, 5278367, 74381793]
```

**程序 2:** 演示中断异常

```
// Java Program to demonstrate take()
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

        // print Dequeue
        // the Deque is empty
        System.out.println("Blocking Deque: " + BD);

        try {
            // throws error as the list is empty
            // and it is interrupted while waiting
            System.out.println("Head of Blocking Deque: "
                               + BD.take());
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**运行时错误:**

```
Max real time limit exceeded due to either by heavy load on server or by using sleep function.
```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blockingdequee . html # take()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#take())