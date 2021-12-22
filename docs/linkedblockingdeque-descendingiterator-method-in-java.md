# Java 中 LinkedBlockingDeque()方法

> 原文:[https://www . geeksforgeeks . org/linkedblockingreque-dependingiterator-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-descendingiterator-method-in-java/)

**的**下行迭代器()**方法链接了锁定命令**并以相反的顺序返回了这个序列中元素的迭代器。元素将按从最后(尾部)到第一(头部)的顺序返回。返回的迭代器是“弱一致”迭代器。

**语法:**

```java
public Iterator descendingIterator()
```

**参数:**此方法不接受任何参数。

**返回:**这个方法以相反的顺序返回一个迭代器。

下面的程序举例说明了*链接锁定请求*的下降畸胎()方法:

**程序 1:**

```java
// Java Program Demonstrate descendingIterator()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)

    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to front of LinkedBlockingDeque
        LBD.addFirst(7855642);
        LBD.addFirst(35658786);
        LBD.addFirst(5278367);
        LBD.addFirst(74381793);

        // Call descendingIterator() method of LinkedBlockingDeque
        Iterator iteratorVals = LBD.descendingIterator();

        // Print elements of iterator
        // created from PriorityBlockingQueue
        System.out.println("The iterator values"
                           + " of LinkedBlockingDeque are:");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

**输出:**

```java
The iterator values of LinkedBlockingDeque are:
7855642
35658786
5278367
74381793

```

**程序二:**

```java
// Java Program Demonstrate descendingIterator()
// method of LinkedBlockingDeque
// when list is of strings

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)

    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<String> LBD
            = new LinkedBlockingDeque<String>();

        // Add numbers to front of LinkedBlockingDeque
        LBD.add("Geeks");
        LBD.add("forGeeks");
        LBD.add("A");
        LBD.add("Computer");
        LBD.add("Portal");

        // Call iterator() method of LinkedBlockingDeque
        Iterator iteratorVals = LBD.descendingIterator();

        // Print elements of iterator
        // created from PriorityBlockingQueue
        System.out.println("The iterator values"
                           + " of LinkedBlockingDeque are:");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

**输出:**

```java
The iterator values of LinkedBlockingDeque are:
Portal
Computer
A
forGeeks
Geeks

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedblockingrequest . html # descendingterar()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#descendingIterator())