# Java 中的 BlockingQueue add()示例

> 原文:[https://www . geeksforgeeks . org/blocking queue-add-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingqueue-add-in-java-with-examples/)

**阻塞队列**接口的 **add(E e)** 方法将参数中传递的元素插入到有空间的队列末尾。如果阻塞队列操作系统容量受限，没有空间可供插入，它将返回一个*非法状态异常*。

**语法:**

```
public void add(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到阻塞队列末尾的元素。

**返回:**该方法在成功插入时返回 true。

例外:

*   **illegalstatexception**:如果此时由于容量限制无法添加元素
*   **空指针异常**:如果指定的元素为空

**注**:**封锁队列**的 **add()** 方法继承了 Java 中的**队列**类。
下面的程序说明了阻塞队列的 add()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate add()
// method of BlockingQueue

import java.util.*;
import java.util.concurrent.BlockingQueue;
import java.util.concurrent.LinkedBlockingDeque;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingQueue
        BlockingQueue<Integer> BQ
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to the BlockingQueue
        BQ.add(7855642);
        BQ.add(35658786);
        BQ.add(5278367);
        BQ.add(74381793);

        // before removing print BlockingQueue
        System.out.println("Blocking Queue: " + BQ);
    }
}
```

**Output**

```
Blocking Queue: [7855642, 35658786, 5278367, 74381793]

```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate add()
// method of LinkedBlockingDeque
// when null is inserted

import java.util.*;
import java.util.concurrent.LinkedBlockingDeque;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> BQ
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        BQ.add(7855642);
        BQ.add(35658786);
        BQ.add(5278367);

        // NULL
        BQ.add(null);

        // before removing print Deque
        System.out.println("Linked Blocking Deque: " + BQ);
    }
}
```

**输出:**

```
Exception in thread "main" java.lang.IllegalStateException: Deque full
    at java.util.concurrent.LinkedBlockingDeque.addLast(LinkedBlockingDeque.java:335)
    at java.util.concurrent.LinkedBlockingDeque.add(LinkedBlockingDeque.java:633)
    at GFG.main(GFG.java:25)
```

**参考:**T2【https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blockingqueue . html # add(E)T4】