# Java 中的 linkedblockingrequeremovelastprocession()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-removelastcoccurrence-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-removelastoccurrence-method-in-java/)

**链接锁定请求**的**移除最后一次出现()**方法从该列表中移除指定元素的最后一次出现。如果 deque 不包含该元素，它将保持不变。如果这个 deque 包含指定的元素，则返回 true，否则返回 false。

**语法:**

```
public boolean removeLastOccurrence(Object o)
```

**参数:**该方法接受一个强制参数 **o** ，该参数指定最后一次出现的元素将从出列容器中移除。

**返回:**该方法返回**真**如果元素存在并从德格容器中移除，否则返回**假**。

下面的程序说明了 link edblockingrequest 的 removeLastOccurrence()方法:

**程序 1:** 当元素存在时。

```
// Java Program to demonstrate removeLastOccurrence()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add(15);
        LBD.add(20);
        LBD.add(20);
        LBD.add(15);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);

        if (LBD.removeLastOccurrence(15))
            System.out.println("Last occurrence of 15 removed");
        else
            System.out.println("15 not present and not removed");

        // prints the Deque after removal
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```
Linked Blocking Deque: [15, 20, 20, 15]
Last occurrence of 15 removed
Linked Blocking Deque: [15, 20, 20]

```

**程序 2:** 当元素不存在时。

```
// Java Program to demonstrate removeLastOccurrence()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add(15);
        LBD.add(20);
        LBD.add(20);
        LBD.add(15);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);

        if (LBD.removeLastOccurrence(10))
            System.out.println("Last occurrence of 10 removed");
        else
            System.out.println("10 not present and not removed");

        // prints the Deque after removal
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```
Linked Blocking Deque: [15, 20, 20, 15]
10 not present and not removed
Linked Blocking Deque: [15, 20, 20, 15]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingrequest . html # removelastpocent-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#removeLastOccurrence-java.lang.Object-)