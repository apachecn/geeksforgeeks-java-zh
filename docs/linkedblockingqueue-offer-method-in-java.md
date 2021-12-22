# JAVA 中的 LinkedBlockingQueue | offer()方法

> 原文:[https://www . geeksforgeeks . org/linkedblockingqueue-offer-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingqueue-offer-method-in-java/)

LinkedBlockingQueue 类有两种类型的 offer()方法:

### 报价(长时间超时，时间单位单位)

**LinkedBlockingQueue** 的**提供(E e，长超时，时间单位单位)**方法，如果队列未满，则在该 LinkedBlockingQueue 的尾部插入作为参数传递给方法的元素。如果 LinkedBlockingQueue 已满，它将等待指定的时间，直到空间变得可用。指定的等待时间和时间单位将作为 offer()方法的参数给出。所以它会等到那个时候，让 LinkedBlockingQueue 移除一些元素，这样这个方法就可以向 LinkedBlockingQueue 添加元素。

**语法:**

```
public boolean offer(E e, long timeout, TimeUnit unit) throws InterruptedException
```

**参数:**该方法接受三个参数:

*   **e**–要插入 LinkedBlockingQueue 的元素。
*   **超时**–offer 方法等待插入新元素的时间已满。
*   **单位**–超时参数的时间单位。

**返回值:**如果元素插入成功，该方法返回*真*。否则，如果在空间可用之前经过了指定的等待时间，它将返回*假*。

**异常:**该方法抛出以下异常:

*   **NullPointRexception**–如果指定的元素为空。
*   **中断异常**–如果在等待时中断。

下面的程序说明了 LinkedBlockingQueue 类的提供(例如，长超时，时间单位单位)方法:

**程序 1:** 使用 offer(E e，长超时，TimeUnit unit)方法插入学生姓名，创建 LinkedBlockingQueue，该方法的 TimeUnit 参数以秒为单位，超时参数为 5 秒。

```
// Java Program Demonstrate
// offer(Element e, long timeout, TimeUnit unit)
// method of LinkedBlockingQueue.

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.TimeUnit;

public class GFG {

    // Main method
    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 4;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Integer>
            linkedQueue = new LinkedBlockingQueue<Integer>(capacityOfQueue);

        // Add 5 elements to ArrayBlockingQueue having
        // Timeout in seconds with value 5 secs in
        // offer(Element e, long timeout, TimeUnit unit)
        System.out.println("adding 32673821 "
                           + linkedQueue.offer(32673821,
                                               5,
                                               TimeUnit.SECONDS));
        System.out.println("adding 88527183: "
                           + linkedQueue.offer(88527183,
                                               5,
                                               TimeUnit.SECONDS));
        System.out.println("adding 431278539: "
                           + linkedQueue.offer(431278539,
                                               5,
                                               TimeUnit.SECONDS));
        System.out.println("adding 351278693: "
                           + linkedQueue.offer(351278693,
                                               5,
                                               TimeUnit.SECONDS));
        System.out.println("adding 647264: "
                           + linkedQueue.offer(647264,
                                               5,
                                               TimeUnit.SECONDS));

        // print the elements of queue
        System.out.println("list of numbers of queue:"
                           + linkedQueue);

        // now queue is full check remaining capacity of queue
        System.out.println("Empty spaces of queue : "
                           + linkedQueue.remainingCapacity());

        // try to add more Integer
        boolean response = linkedQueue.offer(2893476,
                                             5,
                                             TimeUnit.SECONDS);
        System.out.println("Adding new Integer 2893476 is successful: "
                           + response);
    }
}
```

**Output:**

```
adding 32673821 true
adding 88527183: true
adding 431278539: true
adding 351278693: true
adding 647264: false
list of numbers of queue:[32673821, 88527183, 431278539, 351278693]
Empty spaces of queue : 0
Adding new Integer 2893476 is successful: false

```

**程序 2:** 显示报价引发的异常(元素 e，长超时，时间单位单位)方法

```
// Java Program Demonstrate
// offer(Element e, long timeout, TimeUnit unit)
// method of LinkedBlockingQueue.

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.TimeUnit;

public class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 4;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Integer>
            linkedQueue = new LinkedBlockingQueue<Integer>(capacityOfQueue);

        // Add elements to ArrayBlockingQueue having
        // Timeout in seconds with value 5 secs in
        // offer(Element e, long timeout, TimeUnit unit)
        System.out.println("Adding 283239 in Queue :"
                           + linkedQueue.offer(283239,
                                               5,
                                               TimeUnit.SECONDS));

        // try to put null value in offer method
        try {

            System.out.println("Adding null in Queue: "
                               + linkedQueue.offer(null,
                                                   5,
                                                   TimeUnit.SECONDS));
        }
        catch (Exception e) {

            // print error details
            System.out.println("Exception: " + e);
        }

        // print elements of queue
        System.out.println("Items in Queue are "
                           + linkedQueue);
    }
}
```

**Output:**

```
Adding 283239 in Queue :true
Exception: java.lang.NullPointerException
Items in Queue are [283239]

```

### 要约

**LinkedBlockingQueue** 的 **offer(E e)** 方法在这个 LinkedBlockingQueue 的尾部插入作为参数传递的元素 E，如果队列有空间，即队列未满。如果队列已满，则应用 offer()方法不会显示任何效果，因为 LinkedBlockingQueue 将阻止元素插入。当添加到 LinkedBlockingQueue 的操作成功时，offer()方法返回 true，如果该队列已满，则返回 false。此方法优于 add()方法，因为当队列已满时 add 方法会引发错误，但在这种情况下 offer()方法会返回 false。

**语法:**

```
public boolean offer(E e)
```

**参数:**该方法取一个强制参数 **e** ，该参数是要插入到 LinkedBlockingQueue 中的元素。

**返回值:**如果元素插入成功，该方法返回*真*。否则返回*假*。

**异常:**如果指定的元素为空，该方法将抛出**空指针异常**。

下面的程序说明了 LinkedBlockingQueue 类的 offer()方法

**程序 1:** 使用 offer()方法插入学生姓名，创建 LinkedBlockingQueue。

```
// Java Program Demonstrate
// offer(Element e)
// method of LinkedBlockingQueue.

import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 4;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<String>
            linkedQueue = new LinkedBlockingQueue<String>(capacityOfQueue);

        // Add element to LinkedBlockingQueue using offer
        linkedQueue.offer("dean");
        linkedQueue.offer("kevin");
        linkedQueue.offer("sam");
        linkedQueue.offer("jack");

        // print the elements of queue
        System.out.println("list of names of queue:");
        System.out.println(linkedQueue);
    }
}
```

**Output:**

```
list of names of queue:
[dean, kevin, sam, jack]

```

**程序 2:** 检查 LinkedBlockingQueue 是否已满，然后插入新元素。

```
// Java Program Demonstrate
// offer(Element e)
// method of LinkedBlockingQueue.

import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 4;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Integer>
            linkedQueue = new LinkedBlockingQueue<Integer>(capacityOfQueue);

        // Add element to LinkedBlockingQueue using offer
        linkedQueue.offer(34567);
        linkedQueue.offer(45678);
        linkedQueue.offer(98323);
        linkedQueue.offer(93758);

        // print the elements of queue
        System.out.println("list of numbers of queue:");
        System.out.println(linkedQueue);

        // now queue is full check remaining capacity of queue
        System.out.println("Empty spaces of queue : "
                           + linkedQueue.remainingCapacity());

        // try to add extra Integer
        boolean response = linkedQueue.offer(2893476);

        System.out.println("Adding new Integer 2893476 is successful: "
                           + response);

        response = linkedQueue.offer(456751);

        System.out.println("Adding new Integer 456751 is successful: "
                           + response);
    }
}
```

**Output:**

```
list of numbers of queue:
[34567, 45678, 98323, 93758]
Empty spaces of queue : 0
Adding new Integer 2893476 is successful: false
Adding new Integer 456751 is successful: false

```

**程序 3:** 显示 offer()方法引发的异常

```
// Java Program Demonstrate offer(E e)
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 4;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<String> linkedQueue
            = new LinkedBlockingQueue<String>(capacityOfQueue);

        // Add element using offer() method
        linkedQueue.offer("Karan");

        // try to put null value in offer method
        try {
            linkedQueue.offer(null);
        }
        catch (Exception e) {
            // print error details
            System.out.println("Exception: " + e);
        }

        // print elements of queue
        System.out.println("Items in Queue are "
                           + linkedQueue);
    }
}
```

**Output:**

```
Exception: java.lang.NullPointerException
Items in Queue are [Karan]

```

**参考:**

*   [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue . html # offer-E-long-Java . util . concurrent . time unit-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html#offer-E-long-java.util.concurrent.TimeUnit-)
*   [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue . html # offer-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html#offer-E-long-java.util.concurrent.TimeUnit-)