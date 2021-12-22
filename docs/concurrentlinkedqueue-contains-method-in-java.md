# 在 Java 中 ConcurrentLinkedQueue 包含()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedqueue-contains-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkedqueue-contains-method-in-java/)

如果 ConcurrentLinkedQueue 包含作为参数传递的对象 o，则**的**包含()**方法返回真。当且仅当这个 ConcurrentLinkedQueue 包含至少一个等于作为参数传递的对象 o 的元素 e，即 o.equals(e)时，此方法返回 true。**

**语法:**

```
public boolean contains(Object o)
```

**参数:**该方法取一个代表对象的单参数 **O** 来检查 ConcurrentLinkedQueue 是否包含指定的对象。

**返回:**如果这个 ConcurrentLinkedQueue 包含对象，这个方法返回 **true** 。

下面的程序说明了包含()方法的 ConcurrentLinkedQueue:

**例 1:**

```
// Java Program Demonstrate contains()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;

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

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("ConcurrentLinkedQueue: " + queue);

        // check whether queue contains String "Aman"
        boolean response1 = queue.contains("Aman");

        // print after applying contains method
        System.out.println("queue contains String \"Aman\" : "
                           + response1);

        // check whether queue contains "Ram"
        boolean response2 = queue.contains("Ram");

        // print after applying contains method
        System.out.println("queue contains String \"Ram\" : "
                           + response2);
    }
}
```

**输出:**

```
ConcurrentLinkedQueue: [Aman, Amar, Sanjeet, Rabi]
queue contains String "Aman" : true
queue contains String "Ram" : false

```

**例 2:**

```
// Java Program Demonstrate contains()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ConcurrentLinkedQueue
        ConcurrentLinkedQueue<Integer>
            queue = new ConcurrentLinkedQueue<Integer>();

        // Add Numbers to queue
        queue.add(4353);
        queue.add(7824);
        queue.add(78249);
        queue.add(8724);

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("ConcurrentLinkedQueue: " + queue);

        // check whether queue contains 78249
        boolean response1 = queue.contains(78249);

        // print after applying contains method
        System.out.println("queue contains Number 78249 : "
                           + response1);

        // check whether queue contains 9876
        boolean response2 = queue.contains(9876);

        // print after applying contains method
        System.out.println("queue contains Number 9876: "
                           + response2);
    }
}
```

**输出:**

```
ConcurrentLinkedQueue: [4353, 7824, 78249, 8724]
queue contains Number 78249 : true
queue contains Number 9876: false

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentlinkedqueue . html # contains-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedQueue.html#contains-java.lang.Object-)