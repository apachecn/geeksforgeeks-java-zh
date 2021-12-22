# Java 中的 linkedblockingrequeiterator()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-iterator-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-iterator-method-in-java/)

**的**迭代器()**方法以适当的顺序返回这个序列中元素的迭代器。元素将按从第一个(头)到最后一个(尾)的顺序返回。返回的迭代器是“弱一致”迭代器。**

**语法:**

```java
public Iterator iterator()
```

**参数:**此方法不接受任何参数。

**返回:**这个方法返回一个迭代器，以适当的顺序遍历这个对象中的元素。

下面的程序说明了*链接锁定请求*的迭代器()方法:

**程序 1:**

```java
// Java Program Demonstrate iterator()
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

        // Call iterator() method of LinkedBlockingDeque
        Iterator iteratorVals = LBD.iterator();

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
74381793
5278367
35658786
7855642

```

**程序二:**

```java
// Java Program Demonstrate iterator()
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
        Iterator iteratorVals = LBD.iterator();

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
Geeks
forGeeks
A
Computer
Portal

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedblockingrequest . html # iterator()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#iterator())