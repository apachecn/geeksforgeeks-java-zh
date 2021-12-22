# Java 中的 ConcurrentLinkedQueue add()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedqueue-add-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkedqueue-add-method-in-java/)

**ConcurrentLinkedQueue** 的 **add()** 方法用于在这个 ConcurrentLinkedQueue 的尾部插入作为参数传递给 ConcurrentLinkedQueue 的 add()的元素。如果插入成功，此方法返回真。ConcurrentLinkedQueue 是无界的，所以这个方法永远不会抛出 IllegalStateException 或返回 false。

**语法:**

```java
public boolean add(E e)
```

**参数:**该方法采用单个参数 **e** ，该参数表示要插入到该并发链接队列中的元素。

**返回:**该方法在成功插入元素后返回**真**。

**异常:**如果指定的元素为空，该方法抛出**空指针异常**。

下面的程序说明了并发链接队列的 add()方法:

**例 1:** 演示添加字符串的 ConcurrentLinkedQueue 的 add()方法。

```java
// Java Program Demonstrate add()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ConcurrentLinkedQueue
        ConcurrentLinkedQueue<String>
            queue = new ConcurrentLinkedQueue<String>();

        // Add String to queue
        queue.add("Kolkata");
        queue.add("Patna");
        queue.add("Delhi");
        queue.add("Jammu");

        // Displaying the existing ConcurrentLinkedQueue
        System.out.println("ConcurrentLinkedQueue: " + queue);
    }
}
```

**输出:**

```java
ConcurrentLinkedQueue: [Kolkata, Patna, Delhi, Jammu]

```

**例 2:** 演示用于添加数字的 ConcurrentLinkedQueue 的 add()方法。

```java
// Java Program Demonstrate add()
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
    }
}
```

**输出:**

```java
ConcurrentLinkedQueue: [4353, 7824, 78249, 8724]

```

**示例 3:** 演示添加 Null 的 add()方法引发的 NullPointerException。

```java
// Java Program Demonstrate add()
// method of ConcurrentLinkedQueue

import java.util.concurrent.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ConcurrentLinkedQueue
        ConcurrentLinkedQueue<Integer>
            queue = new ConcurrentLinkedQueue<Integer>();

        // Add null to queue
        try {
            queue.add(null);
        }
        catch (NullPointerException e) {
            System.out.println("Exception thrown "
                               + "while adding null: " + e);
        }
    }
}
```

**输出:**

```java
Exception thrown while adding null: java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentlinkedqueue . html # add-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedQueue.html#add-E-)