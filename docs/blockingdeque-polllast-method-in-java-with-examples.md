# Java 中 BlockingDeque pollLast()方法，带示例

> 原文:[https://www . geeksforgeeks . org/blocking eque-poll last-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-polllast-method-in-java-with-examples/)

**blocking eque**的 **pollLast()** 方法返回 Deque 容器中的最后一个元素，并将其删除。如果容器是空的，它将返回**空值**。

**语法:**

```
public E pollLast()
```

**参数:**此方法不接受任何参数。

**返回:**如果容器不为空，该方法返回*德清容器中的最后一个元素*，并删除该元素。如果容器是空的，它将返回*空值*。

**注**:**blocking eque**的 pollLast()方法继承自 Java 中的[link edblocking eque](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类。

下面的程序说明了阻塞请求的 pollLast()方法:

**程序 1:**

```
// Java Program Demonstrate pollLast()
// method of BlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)

    {

        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.addFirst(7855642);
        BD.addFirst(35658786);
        BD.addFirst(5278367);
        BD.addFirst(74381793);

        // Print the queue
        System.out.println("Blocking Deque: " + BD);

        // prints and deletes the last element
        System.out.println("Front element in Deque: " + BD.pollLast());

        // prints the Deque after deletion of last element
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```
Blocking Deque: [74381793, 5278367, 35658786, 7855642]
Front element in Deque: 7855642
Blocking Deque: [74381793, 5278367, 35658786]

```

**程序二:**

```
// Java Program Demonstrate pollLast()
// method of BlockingDeque
// when Deque is empty

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)

    {

        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.add(7855642);
        BD.add(35658786);
        BD.add(5278367);
        BD.add(74381793);

        // Print the queue
        System.out.println("Blocking Deque: " + BD);

        // empty deque
        BD.clear();

        System.out.println("Front element in Deque: " + BD.pollLast());
    }
}
```

**输出:**

```
Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Front element in Deque: null

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blocking request . html # pollast(long，% 20 Java . util . concurrent . time unit)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#pollLast(long, %20java.util.concurrent.TimeUnit))