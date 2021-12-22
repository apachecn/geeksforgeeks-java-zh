# Java 中 BlockingDeque offerLast()方法，带示例

> 原文:[https://www . geeksforgeeks . org/blocking eque-offer last-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-offerlast-method-in-java-with-examples/)

**提供最后一个(E e)** 方法**阻塞请求**将参数中传递的元素插入到 Deque 容器的末尾。如果容器的容量已经超出，那么它不会像 add()和 addLast()函数那样返回异常。

**语法:**

```
public boolean offerLast(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到阻塞请求末尾的元素。

**返回:**这个方法返回*真*如果元素已经插入，否则返回*假。*

**注**:**blocking eque**的 offerLast()方法继承自 Java 中的[link edblocking eque](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类。

下面的程序说明了阻塞请求的 offerLast()方法:

**程序 1:**

```
// Java Program Demonstrate offerLast()
// method of BlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>(4);

        // Add numbers to end of BlockingDeque
        BD.offerLast(7855642);
        BD.offerLast(35658786);
        BD.offerLast(5278367);
        BD.offerLast(74381793);

        // Cannot be inserted
        BD.offerLast(10);

        // cannot be inserted hence returns false
        if (!BD.offerLast(10))
            System.out.println("The element 10 cannot be inserted"
                               + " as capacity is full");

        // before removing print queue
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```
The element 10 cannot be inserted as capacity is full
Blocking Deque: [7855642, 35658786, 5278367, 74381793]

```

**程序二:**

```
// Java Program Demonstrate offerLast()
// method of BlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingDeque
        BlockingDeque<String> BD
            = new LinkedBlockingDeque<String>(4);

        // Add numbers to end of BlockingDeque
        BD.offerLast("abc");
        BD.offerLast("gopu");
        BD.offerLast("geeks");
        BD.offerLast("richik");

        // Cannot be inserted
        BD.offerLast("hii");

        // cannot be inserted hence returns false
        if (!BD.offerLast("hii"))
            System.out.println("The element 'hii' cannot be"
                               + " inserted as capacity is full");

        // before removing print queue
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```
The element 'hii' cannot be inserted as capacity is full
Blocking Deque: [abc, gopu, geeks, richik]

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blocking request . html # offer last(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#offerLast(E))