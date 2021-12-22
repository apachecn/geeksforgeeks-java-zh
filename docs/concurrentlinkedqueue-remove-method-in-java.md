# Java 中的 ConcurrentLinkedQueue remove()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedqueue-remove-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkedqueue-remove-method-in-java/)

**ConcurrentLinkedQueue** 的 **remove(Object o)** 方法用于从该 ConcurrentLinkedQueue 中移除指定元素的单个实例(如果存在的话)。如果这个 ConcurrentLinkedQueue 包含一个或多个这样的元素，这个方法会移除元素 e，使得 o 等于(e)。如果这个 ConcurrentLinkedQueue 包含指定的元素，则 Remove()方法返回 true，否则它将返回 false。

**语法:**

```
public boolean remove(Object o)
```

**参数:**该方法取一个参数 **o** ，代表要从该并发链接队列中删除的元素。

**返回:**如果这个 ConcurrentLinkedQueue 包含指定的元素并被移除，这个方法返回 **true** 。

下面的程序说明了并发链接队列的 remove()方法:

**例 1:**

```
// Java Program Demonstrate remove()
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

        // apply remove() for Number 78249
        boolean response = queue.remove(78249);

        // print results
        System.out.println("Removing Number 78249 successful: " + response);

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("Updated ConcurrentLinkedQueue: " + queue);
    }
}
```

**输出:**

```
ConcurrentLinkedQueue: [4353, 7824, 78249, 8724]
Removing Number 78249 successful: true
Updated ConcurrentLinkedQueue: [4353, 7824, 8724]

```

**例 2:**

```
// Java Program Demonstrate remove()
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

        // apply remove() on queue
        boolean response1 = queue.remove("Aman");

        // print after applying poll method
        System.out.println("Removing String \"Aman\" successful: " + response1);

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("Updated ConcurrentLinkedQueue: " + queue);

        // apply remove() on queue
        boolean response2 = queue.remove("Kisan");

        // print after applying poll method
        System.out.println("Removing String \"Kisan\" successful: " + response2);

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("Updated ConcurrentLinkedQueue: " + queue);
    }
}
```

**输出:**

```
ConcurrentLinkedQueue: [Aman, Amar, Sanjeet, Rabi]
Removing String "Aman" successful: true
Updated ConcurrentLinkedQueue: [Amar, Sanjeet, Rabi]
Removing String "Kisan" successful: false
Updated ConcurrentLinkedQueue: [Amar, Sanjeet, Rabi]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentlinkedqueue . html # remove-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedQueue.html#remove-java.lang.Object-)