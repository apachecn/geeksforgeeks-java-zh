# Java 中 link edblockingrequest remainingCapacity()方法

> 原文:[https://www . geeksforgeeks . org/linkedblockingreque-remainingcapacity-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-remainingcapacity-method-in-java/)

**link edblockingequest**的 **remainingCapacity()** 方法返回这个 deque 在没有阻塞的情况下(在没有内存或资源限制的情况下)可以理想地接受的附加元素的数量。

> 剩余空间()= final _ size()–current _ size()

**语法:**

```
public int remainingCapacity()
```

**参数:**该方法不接受任何参数。

**返回:**这个方法返回可以插入到 deque 容器中的剩余元素数。

下面的程序说明了 link edblockingrequest 的 remainingCapacity()方法:

**程序 1:**

```
// Java Program Demonstrate remainingCapacity()
// method of LinkedBlockingDeque
// when initial size is mentioned

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>(6);

        // Add numbers to end of LinkedBlockingDeque
        LBD.add(7855642);
        LBD.add(35658786);
        LBD.add(5278367);
        LBD.add(74381793);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);
        System.out.println("remainingCapacity = : " + 
                              LBD.remainingCapacity());
    }
}
```

**输出:**

```
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]
remainingCapacity = : 2

```

**程序二:**

```
// Java Program Demonstrate remainingCapacity()
// method of LinkedBlockingDeque
// when no initial size is mentioned

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>(6);

        // Add numbers to end of LinkedBlockingDeque
        LBD.add(7855642);
        LBD.add(35658786);
        LBD.add(5278367);
        LBD.add(74381793);

        // print Dequeue
        System.out.println("Linked Blocking Deque: " + LBD);
        System.out.println("remainingCapacity = " + 
                             LBD.remainingCapacity());
    }
}
```

**输出:**

```
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]
remainingCapacity = 2

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingrequest . html # remainingCapacity–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html#remainingCapacity--)