# Java 中 link edblockingrequest offer first()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-offer first-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-offerfirst-method-in-java/)

**提供**的第一个(E e)** 方法链接锁定请求**将参数中传递的元素插入到 Deque 容器的前面。如果容器的容量已经超出，那么它不会像 add()和 addFirst()函数那样返回异常。

**语法:**

```
public boolean offerFirst(E e)

```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到链接锁定请求前面的元素。

**返回:**这个方法返回*真*如果元素已经插入，否则返回*假。*

下面的程序说明了链接锁定请求的 offerFirst()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate offerFirst()
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
        LBD.offerFirst(7855642);
        LBD.offerFirst(35658786);
        LBD.offerFirst(5278367);
        LBD.offerFirst(74381793);

        // Cannot be inserted
        LBD.offerFirst(10);

        // cannot be inserted hence returns false
        if (!LBD.offerFirst(10))
            System.out.println("The element 10 cannot be inserted"+
                                           " as capacity is full");

        // before removing print queue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**Output:** 

```
The element 10 cannot be inserted as capacity is full
Linked Blocking Deque: [74381793, 5278367, 35658786, 7855642]

```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate offerFirst()
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
        LBD.offerFirst("abc");
        LBD.offerFirst("gopu");
        LBD.offerFirst("geeks");
        LBD.offerFirst("richik");

        // Cannot be inserted
        LBD.offerFirst("hii");

        // cannot be inserted hence returns false
        if (!LBD.offerFirst("hii"))
            System.out.println("The element 'hii' cannot be"
                           +" inserted as capacity is full");

        // before removing print queue
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**Output:** 

```
The element 'hii' cannot be inserted as capacity is full
Linked Blocking Deque: [richik, geeks, gopu, abc]

```

**参考:**T2【https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedblockingrequest . html # offer first(E)T4】