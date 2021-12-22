# Java 中的 BlockingQueue poll()方法，带示例

> 原文:[https://www . geeksforgeeks . org/blocking queue-poll-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingqueue-poll-method-in-java-with-examples/)

**阻塞队列**接口的**轮询(长超时，时间单位单位)**方法通过从队列中移除该元素来返回阻塞队列的头部。可以说，这个方法从这个 LinkedBlockingQueue 的头部检索并移除元素。如果队列为空，那么 poll()方法将等待指定的时间，直到某个元素变为可用。

**语法:**

```
public E poll(long timeout, TimeUnit unit) throws 
```

**参数:**此方法需要两个强制参数:

*   **Timeout** -Waiting time, in units.
*   **Unit** -Time unit of timeout parameter.

**返回值:**这个方法从这个 LinkedBlockingQueue 的头中检索并移除元素，如果在元素可用之前指定的等待时间已经过去，则返回 null。

**异常**如果方法在等待元素可用时中断，此方法将引发**中断异常**。

**注**:**blocking Queue**的 **poll()** 方法继承了 Java 中的 **Queue** 类。

以下程序说明了阻塞队列的轮询(长超时，时间单位单位)方法:

**程序 1** :

```
// Java program to demonstrate
// poll(long timeout, TimeUnit unit)
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;
import java.util.concurrent.TimeUnit;

public class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of BlockingQueue
        int capacityOfQueue = 4;

        // create object of BlockingQueue
        BlockingQueue<String> BQ
            = new LinkedBlockingQueue<String>(capacityOfQueue);

        // Add element to BlockingQueue
        BQ.add("Ravi");
        BQ.add("Suraj");
        BQ.add("Harsh");

        // print elements of queue
        System.out.println("Items in Queue are " + BQ);

        // Try to poll elements from BQ
        // using poll(long timeout, TimeUnit unit) method
        System.out.println("Removing item From head: "
                           + BQ.poll(5, TimeUnit.SECONDS));

        // print queue details
        System.out.println("Now Queue Contains" + BQ);

        // using poll(long timeout, TimeUnit unit) method
        System.out.println("Removing item From head: "
                           + BQ.poll(5, TimeUnit.SECONDS));

        // print queue details
        System.out.println("Now Queue Contains" + BQ);

        // using poll(long timeout, TimeUnit unit) method
        System.out.println("Removing item From head: "
                           + BQ.poll(5, TimeUnit.SECONDS));

        // print queue details
        System.out.println("Now Queue Contains" + BQ);

        // using poll(long timeout, TimeUnit unit) method
        System.out.println("Removing item From head: "
                           + BQ.poll(5, TimeUnit.SECONDS));
        // print queue details
        System.out.println("Now Queue Contains" + BQ);
    }
}
```

**输出:**

```
Items in Queue are [Ravi, Suraj, Harsh]
Removing item From head: Ravi
Now Queue Contains[Suraj, Harsh]
Removing item From head: Suraj
Now Queue Contains[Harsh]
Removing item From head: Harsh
Now Queue Contains[]
Removing item From head: null
Now Queue Contains[]

```

**程序二** :

```
// Java program to demonstrate
// poll(long timeout, TimeUnit unit)
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;
import java.util.concurrent.TimeUnit;

public class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of BlockingQueue
        int capacityOfQueue = 2;

        // create object of BlockingQueue
        BlockingQueue<String> BQ
            = new LinkedBlockingQueue<String>(capacityOfQueue);

        // Add element to BlockingQueue
        BQ.add("Gopal");
        BQ.add("GFG");

        // print elements of queue
        System.out.println("Items in Queue are " + BQ);

        // Try to poll elements from BQ
        // using poll(long timeout, TimeUnit unit) method
        System.out.println("Removing item From head: "
                           + BQ.poll(2, TimeUnit.SECONDS));

        // print queue details
        System.out.println("Now Queue Contains" + BQ);
    }
}
```

**输出:**

```
Items in Queue are [Gopal, GFG]
Removing item From head: Gopal
Now Queue Contains[GFG]

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blockingqueue . html # poll(long，% 20 Java . util . concurrent . time unit)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingQueue.html#poll(long, %20java.util.concurrent.TimeUnit))