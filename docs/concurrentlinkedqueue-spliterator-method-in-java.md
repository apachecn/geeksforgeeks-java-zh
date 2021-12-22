# Java 中的 ConcurrentLinkedQueue spliterator()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedqueue-spliterator-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkedqueue-spliterator-method-in-java/)

**ConcurrentLinkedQueue** 的**分割器()**方法用来获取一个与 ConcurrentLinkedQueue 元素相同的分割器。创建的拆分器弱一致。它可以和 Java 8 中的 Streams 一起使用。此外，它还可以单独和批量遍历元素。Spliterator 是遍历元素的更好方法，因为它对元素提供了更多的控制。

**语法:**

```
public Spliterator spliterator()
```

**返回:**该方法在 ConcurrentLinkedQueue 中的元素上返回一个**拆分器**。

下面的程序说明了 ConcurrentLinkedQueue 的 spliterator()方法:

**例 1:**

```
// Java Program Demonstrate spliterator()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ConcurrentLinkedQueue
        ConcurrentLinkedQueue<Integer>
            queue = new ConcurrentLinkedQueue<Integer>();

        // Add Numbers to queue
        queue.add(4353);
        queue.add(377139);
        queue.add(624378);
        queue.add(654793);
        queue.add(764764);
        queue.add(838494);
        queue.add(632845);

        // create Spliterator of ConcurrentLinkedQueue
        // using spliterator() method
        Spliterator<Integer> spt = queue.spliterator();

        // print result from Spliterator
        System.out.println("list of Numbers:");

        // forEachRemaining method of Spliterator
        spt.forEachRemaining((n) -> System.out.print(n + ", "));
    }
}
```

**输出:**

```
list of Numbers:
4353, 377139, 624378, 654793, 764764, 838494, 632845,

```

**例 2:**

```
// Java Program Demonstrate spliterator()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ConcurrentLinkedQueue
        ConcurrentLinkedQueue<String>
            queue = new ConcurrentLinkedQueue<String>();

        // Add String to queue
        queue.add("Aman");
        queue.add("Amar");
        queue.add("Sanjeet");
        queue.add("Rabi");
        queue.add("Debasis");
        queue.add("Raunak");
        queue.add("Mahesh");

        // create Spliterator of ConcurrentLinkedQueue
        // using spliterator() method
        Spliterator<String> spt = queue.spliterator();

        // print result from Spliterator
        System.out.println("list of Strings:");

        // forEachRemaining method of Spliterator
        spt.forEachRemaining((n) -> System.out.print(n + ", "));
    }
}
```

**输出:**

```
list of Strings:
Aman, Amar, Sanjeet, Rabi, Debasis, Raunak, Mahesh,

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentlinkedqueue . html # spliterator–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedQueue.html#spliterator--)