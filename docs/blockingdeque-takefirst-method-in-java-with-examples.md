# Java 中 BlockingDeque takeFirst()方法，带示例

> 原文:[https://www . geeksforgeeks . org/blocking reque-take first-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-takefirst-method-in-java-with-examples/)

**阻塞请求**的 **takeFirst()** 方法返回并从中移除德奎容器的第一个元素，如有必要，等待直到某个元素可用..如果在等待时被中断，该方法将抛出*中断异常*。

**语法:**

```
public E takeFirst()
```

**返回:**该方法返回德格容器的**第一个元素**，如有必要，等待直到某个元素可用。

**异常**:如果在等待时被中断，该功能会抛出**中断异常**。

**注**:**blocking request**的 **takeFirst()** 方法继承自 Java 中的 LinkedBlockingDeque 类。

下面的程序说明了 link edblockingrequest 的 takeFirst()方法:

**程序 1:**

```
// Java Program to demonstrate takeFirst()
// method of BlockingDeque

import java.util.concurrent.BlockingDeque;
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
                           + BD.takeFirst());

        // prints the Deque
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```
Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Head of Linked Deque: 7855642
Blocking Deque: [35658786, 5278367, 74381793]

```

**程序 2:** 演示中断异常

```
// Java Program to demonstrate takeFirst()
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
        BD.add(7855642);
        BD.add(35658786);
        BD.add(5278367);
        BD.add(74381793);

        // print Dequeue
        System.out.println("Blocking Deque: " + BD);

        BD.clear();

        // throws error as the list is empty and it
        // is interrupted while waiting
        System.out.println("Head of Blocking Deque: "
                           + BD.takeFirst());
    }
}
```

**运行时错误:**

```
Max real time limit exceeded due to either by heavy load on server or by using sleep function

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blockingdequee . html # take first()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#takeFirst())