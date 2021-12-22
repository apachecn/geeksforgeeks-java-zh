# Java 中的 BlockingDeque size()方法，带示例

> 原文:[https://www . geeksforgeeks . org/blocking eque-size-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-size-method-in-java-with-examples/)

**阻塞请求**的**大小()**方法返回德格容器的当前大小。在调用该函数时，将返回 Deque 容器中的元素数量。如果容器是容量受限的，那么它还返回在函数调用时容器中存在的元素的数量。

**语法:**

```
public int size()
```

**返回:**该方法返回一个**整数**值，表示容器中的元素数量。

**注**:**blocking request**的 **size()** 方法继承自 Java 中的 LinkedBlockingDeque 类。

下面的程序举例说明了大小()方法的阻塞请求:

**程序 1:**

```
// Java Program to demonstrate public int size()
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
        BD.add(15);
        BD.add(20);
        BD.add(20);
        BD.add(15);

        // print Deque
        System.out.println("Blocking Deque: " + BD);

        // prints the Deque after removal
        System.out.println("Size of Blocking Deque: "
                           + BD.size());
    }
}
```

**输出:**

```
Blocking Deque: [15, 20, 20, 15, 15, 20, 20, 15]
Size of Blocking Deque: 8

```

**程序二:**

```
// Java Program to demonstrate public int size()
// method of BlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of BlockingDeque
        BlockingDeque<String> BD
            = new LinkedBlockingDeque<String>();

        // Add numbers to end of BlockingDeque
        BD.add("geeks");
        BD.add("forGeeks");
        BD.add("A Computer");
        BD.add("Portal");

        // print Dequeue
        System.out.println("Blocking Deque: " + BD);

        // prints the Deque after removal
        System.out.println("Size of Blocking Deque: "
                           + BD.size());
    }
}
```

**输出:**

```
Blocking Deque: [geeks, forGeeks, A Computer, Portal]
Size of Blocking Deque: 4

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blockingdequee . html # size()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#size())