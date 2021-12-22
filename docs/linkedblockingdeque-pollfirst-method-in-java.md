# Java 中 link edblockingrequepollsfirst()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-poll first-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-pollfirst-method-in-java/)

**的**pollsfirst()**方法将链接锁定请求**返回到 Deque 容器中的前端元素，并将其删除。如果容器是空的，它将返回**空值**。

**语法:**

```
public E pollFirst()
```

**参数:**此方法不接受任何参数。

**返回:**如果容器不是空的，这个方法返回*前元素*在德清容器中，并删除该元素。如果容器是空的，它将返回*空值*。

下面的程序说明了链接锁定请求的 pollFirst()方法:

**程序 1:**

```
// Java Program Demonstrate pollFirst()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)

    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.addFirst(7855642);
        LBD.addFirst(35658786);
        LBD.addFirst(5278367);
        LBD.addFirst(74381793);

        // Print the queue
        System.out.println("Linked Blocking Deque: " + LBD);

        // prints and deletes
        System.out.println("Front element in Deque: " + LBD.pollFirst());

        // Deque after deletion of front element
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```
Linked Blocking Deque: [74381793, 5278367, 35658786, 7855642]
Front element in Deque: 74381793
Linked Blocking Deque: [5278367, 35658786, 7855642]

```

**程序二:**

```
// Java Program Demonstrate pollFirst()
// method of LinkedBlockingDeque
// when Deque is empty

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)

    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add(7855642);
        LBD.add(35658786);
        LBD.add(5278367);
        LBD.add(74381793);

        // Print the queue
        System.out.println("Linked Blocking Deque: " + LBD);

        // empty deque
        LBD.clear();

        System.out.println("Front element in Deque: " + LBD.pollFirst());
    }
}
```

**输出:**

```
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Front element in Deque: null

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedblockingrequest . html # pollsfirst()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#pollFirst())