# Java 中的 BlockingDeque remove()方法，示例

> 原文:[https://www . geeksforgeeks . org/blocking reque-remove-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-remove-method-in-java-with-examples/)

**移出()**方法**封锁**移出德格集装箱的头部。如果德奎容器是空的，该方法抛出一个 *NoSuchElementException* 。如果参数中传入了一个元素，它将移除给定的元素(如果存在于 Deque 中)。

**语法:**

```
public E remove() or boolean remove(element)
```

**参数:**该方法接受一个临时参数元素，该元素将从阻塞请求中删除

**返回:**如果参数被传递，该方法返回真或假，否则不返回任何内容。如果元素在 Deque 中，则返回 true，否则返回 false。

**异常**:如果德格为空，该函数抛出 *NoSuchElementException* 。

**注意**:**blocking request**的 **remove()** 方法继承自 Java 中的 LinkedBlockingDeque 类。

下面的程序说明了删除()方法的阻塞请求:

**程序 1:**

```
// Java Program Demonstrate remove()
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
        BD.add(7855642);
        BD.add(35658786);
        BD.add(5278367);
        BD.add(74381793);

        // print Deque
        System.out.println("Blocking Deque: " + BD);

        // removes the front element
        BD.remove();
        System.out.println("Blocking Deque: " + BD);

        // removes the element
        BD.remove(5278367);
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```
Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Blocking Deque: [35658786, 5278367, 74381793]
Blocking Deque: [35658786, 74381793]

```

**节目 2:**

```
// Java Program Demonstrate remove()
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
        BD.add(7855642);
        BD.add(35658786);
        BD.add(5278367);
        BD.add(74381793);

        // print Deque
        System.out.println("Blocking Deque: " + BD);

        BD.clear();

        // removes the front element
        BD.remove();
        System.out.println("Blocking Deque: " + BD);

        // removes the element
        BD.remove(5278367);
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```
Exception in thread "main" java.util.NoSuchElementException
    at java.util.concurrent.LinkedBlockingDeque.removeFirst(LinkedBlockingDeque.java:453)
    at java.util.concurrent.LinkedBlockingDeque.remove(LinkedBlockingDeque.java:672)
    at GFG.main(GFG.java:29)

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blockingdequee . html # remove()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#remove())