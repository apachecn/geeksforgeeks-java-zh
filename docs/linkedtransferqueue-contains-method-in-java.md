# Java 中 LinkedTransferQueue 包含()方法

> 原文:[https://www . geeksforgeeks . org/linkedtransferqueue-contains-method-in-Java/](https://www.geeksforgeeks.org/linkedtransferqueue-contains-method-in-java/)

**java . util . concurrent . linkedtransferqueue**的 **contains()** 方法是 Java 中的一个内置函数，如果指定的元素出现在这个队列中，它将返回一个真布尔值，否则返回 false。

**语法:**

```
LinkedTransferQueue.contains(Object o)
```

**参数:**该函数接受单个参数 *o* ，即检查该队列中是否存在该参数。

**返回值:**该函数返回一个布尔值。如果该队列中存在指定的元素，则返回真，否则返回假。

下面的程序说明了 LinkedTransferQueue.contains()方法:

**程序 1:**

```
// Java Program Demonstrate contains()
// method of LinkedTransferQueue

import java.util.concurrent.*;

class LinkedTransferQueueContainsExample1 {
    public static void main(String[] args)
    {

        // Initializing the queue
        LinkedTransferQueue<Integer>
            queue = new LinkedTransferQueue<Integer>();

        // Adding elements to this queue
        for (int i = 10; i <= 15; i++)
            queue.add(i);

        // Checks if 9 is present in the queue
        if (queue.contains(9))
            System.out.println("9 is present in the queue.");
        else
            System.out.println("9 is not present in the queue.");
    }
}
```

**输出:**

```
9 is not present in the queue.

```

**程序二:**

```
// Java Program Demonstrate contains()
// method of LinkedTransferQueue */

import java.util.concurrent.*;

class LinkedTransferQueueContainsExample2 {
    public static void main(String[] args)
    {

        // Initializing the queue
        LinkedTransferQueue<String>
            queue = new LinkedTransferQueue<String>();

        // Adding elements to this queue
        queue.add("Gfg");
        queue.add("is");
        queue.add("fun");

        // Checks if Gfg is present in the queue
        if (queue.contains("Gfg"))
            System.out.println("Gfg is present in the queue.");
        else
            System.out.println("Gfg is not present in the queue.");
    }
}
```

**输出:**

```
Gfg is present in the queue.

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedtransferqueue . html #包含(java.lang.Object)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedTransferQueue.html#contains(java.lang.Object))