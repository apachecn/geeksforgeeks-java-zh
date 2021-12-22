# Java 中的 linkedblockingrequeofflast()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-offer last-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-offerlast-method-in-java/)

**的**offlast(E E)**方法链接锁定请求**将参数中传递的元素插入到 Deque 容器的末尾。如果容器的容量已经超出，那么它不会像 add()和 addLast()函数那样返回异常。

**语法:**

```java
public boolean offerLast(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到链接锁定请求末尾的元素。

**返回:**这个方法返回*真*如果元素已经插入，否则返回*假。*

下面的程序说明了链接锁定请求的 offlester()方法:

**程序 1:**

```java
// Java Program Demonstrate offerLast()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>(4);

        // Add numbers to end of LinkedBlockingDeque
        LBD.offerLast(7855642);
        LBD.offerLast(35658786);
        LBD.offerLast(5278367);
        LBD.offerLast(74381793);

        // Cannot be inserted
        LBD.offerLast(10);

        // cannot be inserted hence returns false
        if (!LBD.offerLast(10))
            System.out.println("The element 10 cannot be inserted"+
                                            " as capacity is full");

        // before removing print queue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```java
The element 10 cannot be inserted as capacity is full
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]

```

**程序二:**

```java
// Java Program Demonstrate offerLast()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<String> LBD
            = new LinkedBlockingDeque<String>(4);

        // Add numbers to end of LinkedBlockingDeque
        LBD.offerLast("abc");
        LBD.offerLast("gopu");
        LBD.offerLast("geeks");
        LBD.offerLast("richik");

        // Cannot be inserted
        LBD.offerLast("hii");

        // cannot be inserted hence returns false
        if (!LBD.offerLast("hii"))
            System.out.println("The element 'hii' cannot be"+
                             " inserted as capacity is full");

        // before removing print queue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```java
The element 'hii' cannot be inserted as capacity is full
Linked Blocking Deque: [abc, gopu, geeks, richik]

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedblockingrequest . html # offer last(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#offerLast(E))