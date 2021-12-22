# Java 中的 LinkedBlockingDeque peekLast()方法

> 原文:[https://www . geeksforgeeks . org/linkedblockingreque-peek last-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-peeklast-method-in-java/)

**link edblockingrequest**的 **peekLast()** 方法返回了 Deque 容器中的最后一个元素，但没有删除它。如果容器是空的，它将返回**空值**。

**语法:**

```
public E peekLast()
```

**参数:**此方法不接受任何参数。

**返回:**如果容器不是空的，这个方法返回*德清容器中的最后一个元素*。如果容器为空，则返回 false。

下面的程序说明了 linkedblockingrequest 的 peekLast()方法:

**程序 1:**

```
// Java Program Demonstrate peekLast()
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

        System.out.println("Front element in Deque: " + LBD.peekLast());
    }
}
```

**输出:**

```
Linked Blocking Deque: [74381793, 5278367, 35658786, 7855642]
Front element in Deque: 7855642

```

**程序二:**

```
// Java Program Demonstrate peekLast()
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

        System.out.println("Front element in Deque: " + LBD.peekLast());
    }
}
```

**输出:**

```
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Front element in Deque: null

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedblockingrequest . html # peekLast()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#peekLast())