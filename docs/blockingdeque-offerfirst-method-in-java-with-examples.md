# Java 中 BlockingDeque offerFirst()方法，带示例

> 原文:[https://www . geeksforgeeks . org/blocking eque-offer first-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-offerfirst-method-in-java-with-examples/)

**提供**阻塞请求**的 First(E e)** 方法，将参数中传递的元素插入到 Deque 容器的前面。如果容器的容量已经超出，那么它不会像 add()和 addFirst()函数那样返回异常。

**语法:**

```java
public boolean offerFirst(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到阻塞请求前面的元素。

**返回:**这个方法返回*真*如果元素已经插入，否则返回*假。*

**注**:**blocking eque**的 offerFirst()方法继承自 Java 中的[link edblocking eque](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类。

下面的程序说明了链接锁定请求的 offerFirst()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate offerFirst()
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
        BD.offerFirst(7855642);
        BD.offerFirst(35658786);
        BD.offerFirst(5278367);
        BD.offerFirst(74381793);

        // Cannot be inserted
        BD.offerFirst(10);

        // cannot be inserted hence returns false
        if (!BD.offerFirst(10))
            System.out.println("The element 10 cannot be inserted"
                               + " as capacity is full");

        // before removing print queue
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**Output:** 

```java
The element 10 cannot be inserted as capacity is full
Blocking Deque: [74381793, 5278367, 35658786, 7855642]
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate offerFirst()
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
        BD.offerFirst("abc");
        BD.offerFirst("gopu");
        BD.offerFirst("geeks");
        BD.offerFirst("richik");

        // Cannot be inserted
        BD.offerFirst("hii");

        // cannot be inserted hence returns false
        if (!BD.offerFirst("hii"))
            System.out.println("The element 'hii' cannot be"
                               + " inserted as capacity is full");

        // before removing print queue
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**Output:** 

```java
The element 'hii' cannot be inserted as capacity is full
Blocking Deque: [richik, geeks, gopu, abc]
```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blocking request . html # offer first(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#offerFirst(E))