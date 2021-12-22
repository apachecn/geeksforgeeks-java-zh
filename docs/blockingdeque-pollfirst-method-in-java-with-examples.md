# Java 中 BlockingDeque pollFirst()方法，带示例

> 原文:[https://www . geeksforgeeks . org/blocking eque-poll first-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-pollfirst-method-in-java-with-examples/)

**blocking eque**的**pollsfirst()**方法返回 Deque 容器中的前元素，并将其删除。如果容器是空的，它将返回**空值**。

**语法:**

```java
public E pollFirst()
```

**参数:**此方法不接受任何参数。

**返回:**如果容器不是空的，这个方法返回*前元素*在德清容器中，并删除该元素。如果容器是空的，它将返回*空值*。

**注**:**blocking eque**的 pollFirst()方法继承自 Java 中的[link edblocking eque](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类。

下面的程序说明了 pollFirst()阻塞请求的方法:

**程序 1:**

```java
// Java Program Demonstrate pollFirst()
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

        // prints and deletes
        System.out.println("Front element in Deque: " + BD.pollFirst());

        // Deque after deletion of front element
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```java
Blocking Deque: [74381793, 5278367, 35658786, 7855642]
Front element in Deque: 74381793
Blocking Deque: [5278367, 35658786, 7855642]

```

**程序二:**

```java
// Java Program Demonstrate pollFirst()
// method of BlockingDeque
// when Deque is empty

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)

    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> BD
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

        System.out.println("Front element in Deque: " + BD.pollFirst());
    }
}
```

**输出:**

```java
Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Front element in Deque: null

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blockingdequehtml # poll first(long，% 20 Java . util . concurrent . time unit)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#pollFirst(long, %20java.util.concurrent.TimeUnit))