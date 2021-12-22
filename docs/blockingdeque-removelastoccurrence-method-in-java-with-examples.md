# Java 中的 blocking request removelastprocession()方法，带示例

> 原文:[https://www . geeksforgeeks . org/blocking reque-removelastcoccurrence-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-removelastoccurrence-method-in-java-with-examples/)

**移除最后一次出现()**方法**阻塞请求**从该命令中移除指定元素的最后一次出现。如果 deque 不包含该元素，它将保持不变。如果这个 deque 包含指定的元素，则返回 true，否则返回 false。

**语法:**

```java
public boolean removeLastOccurrence(Object o)
```

**参数:**该方法接受一个强制参数 **o** ，该参数指定最后一次出现的元素将从出列容器中移除。

**返回:**该方法返回**真**如果元素存在并从德格容器中移除，否则返回**假**。

**注意**:**blocking equation**的**removelastpocation()**方法继承自 Java 中的 LinkedBlockingDeque 类。

下面的程序说明了阻止请求的 removeLastOccurrence()方法:

**程序 1:** 当元素存在时。

```java
// Java Program to demonstrate removeLastOccurrence()
// method of BlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.add(15);
        BD.add(20);
        BD.add(20);
        BD.add(15);

        // print Dequeue
        System.out.println("Blocking Deque: " + BD);

        if (BD.removeLastOccurrence(15))
            System.out.println("Last occurrence of 15 removed");
        else
            System.out.println("15 not present and not removed");

        // prints the Deque after removal
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```java
Blocking Deque: [15, 20, 20, 15]
Last occurrence of 15 removed
Blocking Deque: [15, 20, 20]

```

**程序 2:** 当元素不存在时。

```java
// Java Program to demonstrate removeLastOccurrence()
// method of BlockingDeque

import java.util.concurrent.BlockingDeque;
import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.add(15);
        BD.add(20);
        BD.add(20);
        BD.add(15);

        // print Deque
        System.out.println("Blocking Deque: " + BD);

        if (BD.removeLastOccurrence(10))
            System.out.println("Last occurrence of 10 removed");
        else
            System.out.println("10 not present and not removed");

        // prints the Deque after removal
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```java
Blocking Deque: [15, 20, 20, 15]
10 not present and not removed
Blocking Deque: [15, 20, 20, 15]

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blocking request . html # removeLastOccurrence(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#removeLastOccurrence(java.lang.Object))