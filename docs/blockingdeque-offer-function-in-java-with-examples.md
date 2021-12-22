# 用示例在 Java 中阻塞请求提供()函数

> 原文:[https://www . geeksforgeeks . org/blocking eque-offer-function-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-offer-function-in-java-with-examples/)

**提供**阻塞请求**的(E e)** 方法，将参数中传递的元素插入到数据的末尾。如果容器的容量已经超出，那么它不会像 add()和 addFirst()函数那样返回异常。

**语法:**

```java
public boolean offer(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到阻塞请求末尾的元素。

**返回:**这个方法返回*真*如果元素已经插入，否则返回*假。*

**注**:**blocking eque**的 offer()方法继承了 Java 中[link edblocking eque](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类。

下面的程序说明了提供()阻塞请求的方法:

**程序 1:**

```java
// Java Program Demonstrate offer()
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
        BD.offer(7855642);
        BD.offer(35658786);
        BD.offer(5278367);
        BD.offer(74381793);

        // Cannot be inserted
        BD.offer(10);

        // cannot be inserted hence returns false
        if (!BD.offer(10))
            System.out.println("The element 10 cannot be inserted"
                               + " as capacity is full");

        // before removing print queue
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```java
The element 10 cannot be inserted as capacity is full
Blocking Deque: [7855642, 35658786, 5278367, 74381793]

```

**程序二:**

```java
// Java Program Demonstrate offer()
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
        BD.offer("abc");
        BD.offer("gopu");
        BD.offer("geeks");
        BD.offer("richik");

        // Cannot be inserted
        BD.offer("hii");

        // cannot be inserted hence returns false
        if (!BD.offer("hii"))
            System.out.println("The element 'hii' cannot be inserted"
                               + " as capacity is full");

        // before removing print queue
        System.out.println("Linked Blocking Deque: " + BD);
    }
}
```

**输出:**

```java
The element 'hii' cannot be inserted as capacity is full
Blocking Deque: [abc, gopu, geeks, richik]

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blockingdequee . html # offer(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#offer(E))