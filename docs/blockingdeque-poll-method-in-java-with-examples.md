# Java 中 BlockingDeque poll()方法，带示例

> 原文:[https://www . geeksforgeeks . org/blocking eque-poll-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-poll-method-in-java-with-examples/)

**blocking request**的 **poll()** 方法返回 Deque 容器中的前元素并删除它。如果容器是空的，它将返回**空值**。

**语法:**

```
public E poll()
```

**参数:**此方法不接受任何参数。

**返回:**如果容器不是空的，这个方法返回*德清容器的前元素*并删除它。如果容器是空的，它将返回*空值*。

**注**:**blocking eque**的 poll()方法继承自 Java 中的[link edblocking eque](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类。

下面的程序说明了阻塞请求的轮询()方法:

**程序 1:**

```
// Java Program Demonstrate poll()
// method of BlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque import java.util.*;

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

        System.out.println("Front element in Deque: " + BD.poll());

        // One element is deleted as poll was called
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```
Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Front element in Deque: 7855642
Blocking Deque: [35658786, 5278367, 74381793]

```

**程序二:**

```
// Java Program Demonstrate poll()
// method of BlockingDeque
// when Deque is empty

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque import java.util.*;

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

        System.out.println("Front element in Deque: " + BD.poll());
    }
}
```

**输出:**

```
Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Front element in Deque: null

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blocking request . html # poll(long，% 20 Java . util . concurrent . time unit)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#poll(long, %20java.util.concurrent.TimeUnit))