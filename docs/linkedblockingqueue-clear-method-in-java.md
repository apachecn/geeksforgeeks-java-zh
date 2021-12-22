# Java 中 LinkedBlockingQueue clear()方法

> 原文:[https://www . geeksforgeeks . org/linkedblockingqueue-clear-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingqueue-clear-method-in-java/)

LinkedBlockingQueue 的 **clear()** 方法从该队列中移除所有元素。应用此方法后，队列将变空。

**语法:**

```
public void clear()
```

下面的程序说明了 LinkedBlockingQueue 类的 clear()方法:

**程序 1:**

```
// Java Program Demonstrate clear()
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 50;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Integer> linkedQueue
            = new LinkedBlockingQueue<Integer>(capacityOfQueue);

        // Add element to LinkedBlockingQueue
        linkedQueue.add(2300);
        linkedQueue.add(1322);
        linkedQueue.add(8945);
        linkedQueue.add(6512);

        // print queue
        System.out.println("LinkedBlockingQueue before using"
                           + " clear() : " + linkedQueue);

        // Apply clear() method
        linkedQueue.clear();

        // print queue
        System.out.println();
        System.out.println("LinkedBlockingQueue after using"
                           + " clear() method : " + linkedQueue);
    }
}
```

**Output:**

```
LinkedBlockingQueue before using clear() : [2300, 1322, 8945, 6512]

LinkedBlockingQueue after using clear() method : []

```

**程序二:**

```
// Java Program Demonstrate clear()
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 50;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<String> names
            = new LinkedBlockingQueue<String>(capacityOfQueue);

        // Add element to ArrayBlockingQueue
        names.add("Shubham");
        names.add("Siddhant");
        names.add("Mahafuj");
        names.add("Arka");
        names.add("Raunak");

        // print queue
        System.out.println("LinkedBlockingQueue before using"
                           + " clear() : " + names);

        // Apply clear() method
        names.clear();

        // print queue
        System.out.println();
        System.out.println("LinkedBlockingQueue after using"
                           + " clear() method : " + names);
    }
}
```

**输出:**

```
LinkedBlockingQueue before using clear() : [Shubham, Siddhant, Mahafuj, Arka, Raunak]

LinkedBlockingQueue after using clear() method : []

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue . html # clear–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html#clear--)