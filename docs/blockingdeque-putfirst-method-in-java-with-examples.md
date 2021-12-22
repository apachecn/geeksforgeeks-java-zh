# Java 中的 BlockingDeque putFirst()方法，带示例

> 原文:[https://www . geeksforgeeks . org/blocking eque-put first-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-putfirst-method-in-java-with-examples/)

**阻塞请求**的 **putFirst(E e)** 方法将指定的元素插入到这个命令所代表的队列的前面。如果德奎是容量受限的，那么它将等待空间变得可用。

**语法:**

```
public void putFirst(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到阻塞请求前面的元素。

**返回:**此方法不返回任何内容。

**异常:**程序抛出如下所示的两个异常:

*   **null pointerexception** -If the specified element is empty
*   **Interrupt exception** –If you interrupt while waiting

**注**:**blocking eque**的 putFirst()方法继承自 Java 中的[link edblocking eque](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类。

下面的程序说明了 putFirst()方法的阻塞请求:

**程序 1:**

```
// Java Program Demonstrate putFirst()
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
        BD.putFirst(7855642);
        BD.putFirst(35658786);
        BD.putFirst(5278367);
        BD.putFirst(74381793);

        // print Deque
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```
Blocking Deque: [74381793, 5278367, 35658786, 7855642]

```

**节目 2:**

```
// Java Program Demonstrate putFirst()
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
        BD.putFirst(7855642);
        BD.putFirst(35658786);
        BD.putFirst(5278367);

        // throws an exception
        BD.putFirst(null);

        // print Dequeue
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出** :

```
Exception in thread "main" java.lang.NullPointerException
    at java.util.concurrent.LinkedBlockingDeque.putFirst(LinkedBlockingDeque.java:373)
    at GFG.main(GFG.java:24)

```

**节目 3:**

```
// Java Program Demonstrate putFirst()
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
        BD.putFirst(7855642);
        BD.putFirst(35658786);
        BD.putFirst(5278367);

        // throws an exception
        BD.putFirst(4356789);

        // print Dequeue
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出** :

```
Max real time limit exceeded due to either by heavy load on server or by using sleep function

```

**参考:**T2【https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blockingdequee . html # putFirst(E)