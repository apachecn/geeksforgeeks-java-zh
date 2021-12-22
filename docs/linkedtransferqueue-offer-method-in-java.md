# Java 中 LinkedTransferQueue offer()方法

> 原文:[https://www . geeksforgeeks . org/link edtransferqueue-offer-method-in-Java/](https://www.geeksforgeeks.org/linkedtransferqueue-offer-method-in-java/)

### 报价(长时间超时，时间单位单位)

类**的**方法提供(E e，长超时，时间单位单位)**是一个内置的 java 函数，如果队列没有满，它会在这个队列的尾部插入作为参数传递给方法的元素。**

*   如果 LinkedTransferQueue 已满，它将等待指定的时间，直到空间变得可用。
*   指定的等待时间和时间单位将作为参数提供给 offer 方法，因此它将等到该时间，以便 LinkedTransferQueue 删除一些元素，以便 offer 方法可以向 LinkedTransferQueue 添加元素。

**语法:**

```
public boolean offer(E e, long timeout, TimeUnit unit)
```

**参数:**函数接受以下参数:

*   **e**–要插入的元素。
*   **超时**
*   **单位**–决定如何解释超时参数的时间单位

**返回值:**该方法返回一个布尔值**真**。由于队列是无界的，这个方法永远不会阻塞或返回 false。

**异常:**当指定元素为空时，函数显示**空指针异常**。

下面的程序说明了 Java . util . concurrent . linkedtransferqueue . offer()的使用:

**程序 1:** 通过使用 offer(E e，长超时，时间单位)方法插入学生姓名来创建 LinkedTransferQueue，该方法的时间单位参数以秒为单位，超时参数为 5 秒

```
// Java Program Demonstrate offer()
// method of LinkedTransferQueue

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of LinkedTransferQueue
        LinkedTransferQueue<Integer>
            queue = new LinkedTransferQueue<Integer>();

        // Add 5 elements to ArrayBlockingQueue having
        // Timeout in seconds with value 5 secs in
        // offer(Element e, long timeout, TimeUnit unit)

        System.out.println("adding 15 "
                           + queue.offer(15, 5, TimeUnit.SECONDS));
        System.out.println("adding 25: "
                           + queue.offer(25, 5, TimeUnit.SECONDS));
        System.out.println("adding 35: "
                           + queue.offer(35, 5, TimeUnit.SECONDS));
        System.out.println("adding 45: "
                           + queue.offer(45, 5, TimeUnit.SECONDS));
        System.out.println("adding 55: "
                           + queue.offer(55, 5, TimeUnit.SECONDS));

        // print the elements of queue
        System.out.println("list of numbers of queue: "
                           + queue);
    }
}
```

**Output:**

```
adding 15 true
adding 25: true
adding 35: true
adding 45: true
adding 55: true
list of numbers of queue: [15, 25, 35, 45, 55]

```

**程序 2:** 显示空指针异常的程序。

```
// Java Program Demonstrate offer()
// method of LinkedTransferQueue

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // Initializing the queue
        LinkedTransferQueue<Integer>
            queue = new LinkedTransferQueue<Integer>();

        // add elements to queue
        try {
            queue.offer(null, 5, TimeUnit.SECONDS);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
Exception: java.lang.NullPointerException

```

### 要约

**java . util . concurrent . LinkedTransferQueue**类的 **offer(E e)** 方法是 Java 中的一个内置函数，如果队列有空间，即队列未满，它会在这个 LinkedTransferQueue 的尾部插入作为参数传递给方法的元素 E。如果队列已满，则应用 offer()方法不会显示任何效果，因为 LinkedTransferQueue 将阻止元素插入。当添加到 LinkedTransferQueue 的操作成功时，offer()方法返回 true，如果该队列已满，则返回 false。此方法优于 add()方法，因为当队列已满时 add 方法会引发错误，但在这种情况下 offer()方法会返回 false。

**语法:**

```
public boolean offer(E e)
```

**参数:**该函数接受单个参数 **e** ，即要插入的元素。

**返回值:**该方法在成功插入后返回**真**。

**异常:**当指定元素为空时，函数显示**空指针异常**。

**程序 1:** 在队列中添加字符串。

```
// Java Program Demonstrate offer()
// method of LinkedTransferQueue

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
    {

        // Initializing the queue
        LinkedTransferQueue<String>
            queue = new LinkedTransferQueue<String>();

        // Adding elements to this queue
        queue.offer("alex");
        queue.offer("bob");
        queue.offer("chuck");
        queue.offer("drake");
        queue.offer("eric");

        // Printing the elements of the queue
        System.out.print("Queue: ");
        for (String i : queue)
            System.out.print(i + " ");
    }
}
```

**Output:**

```
Queue: alex bob chuck drake eric

```

**程序 2:** 显示空指针异常的程序。

```
// Java Program Demonstrate offer()
// method of LinkedTransferQueue

import java.util.concurrent.LinkedTransferQueue;

class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // Initializing the queue
        LinkedTransferQueue<Integer>
            queue = new LinkedTransferQueue<Integer>();

        // add elements to queue
        queue.offer(10);
        queue.offer(20);
        queue.offer(30);

        try {
            queue.offer(null);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
Exception: java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedtransferqueue . html # offer(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedTransferQueue.html#offer(E))
T5】https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedtransferqueue . html # offer(E，%20long，% 20 Java . util . concurrent . time unit)