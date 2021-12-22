# Java 中的 LinkedBlockingDeque peekFirst()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-peek first-in-method-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-peekfirst-method-in-java/)

**的 **peekFirst()** 方法 link edblockingrequest**返回 Deque 容器中的 front 元素，但不删除它。如果容器是空的，它将返回**空值**。

**语法:**

```java
public E peekFirst()
```

**参数:**此方法不接受任何参数。

**返回:**如果容器不是空的，该方法返回德清容器中的*前元素*。如果容器是空的，它将返回*空值*。

下面的程序说明了链接锁定请求的 peekFirst()方法:

**程序 1:**

```java
// Java Program Demonstrate peekFirst()
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

        System.out.println("Front element in Deque: " + 
                                        LBD.peekFirst());
    }
}
```

**输出:**

```java
Linked Blocking Deque: [74381793, 5278367, 35658786, 7855642]
Front element in Deque: 74381793

```

**程序二:**

```java
// Java Program Demonstrate peekFirst()
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

        System.out.println("Front element in Deque: " + 
                                          LBD.peekFirst());
    }
}
```

**输出:**

```java
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Front element in Deque: null

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedblockingrequest . html # peek first()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#peekFirst())