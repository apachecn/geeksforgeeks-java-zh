# Java 中的 BlockingDeque iterator()方法，带示例

> 原文:[https://www . geeksforgeeks . org/blockingrequest-iterator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-iterator-method-in-java-with-examples/)

**blocking eque**的**迭代器()**方法以适当的顺序返回这个序列中元素的迭代器。元素将按从第一个(头)到最后一个(尾)的顺序返回。返回的迭代器是“弱一致”迭代器。

**语法:**

```java
public Iterator iterator()
```

**参数:**此方法不接受任何参数。

**返回:**这个方法返回一个迭代器，以适当的顺序遍历这个对象中的元素。

**注**:**blocking eque**的迭代器()方法是从 Java 中的[link edblocking eque](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类继承而来的。

以下程序说明了*阻塞请求*的迭代器()方法:

**程序 1:**

```java
// Java Program Demonstrate iterator()
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

        // Add numbers to front of BlockingDeque
        BD.addFirst(7855642);
        BD.addFirst(35658786);
        BD.addFirst(5278367);
        BD.addFirst(74381793);

        // Call iterator() method of BlockingDeque
        Iterator iteratorVals = BD.iterator();

        // Print elements of iterator
        // created from PriorityBlockingQueue
        System.out.println("The iterator values"
                           + " of BlockingDeque are:");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

**输出:**

```java
The iterator values of BlockingDeque are:
74381793
5278367
35658786
7855642

```

**程序二:**

```java
// Java Program Demonstrate iterator()
// method of BlockingDeque
// when list is of strings

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)

    {

        // create object of BlockingDeque
        BlockingDeque<String> BD
            = new LinkedBlockingDeque<String>();

        // Add numbers to front of BlockingDeque
        BD.add("Geeks");
        BD.add("forGeeks");
        BD.add("A");
        BD.add("Computer");
        BD.add("Portal");

        // Call iterator() method of BlockingDeque
        Iterator iteratorVals = BD.iterator();

        // Print elements of iterator
        // created from BlockingQueue
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
The iterator values of BlockingDeque are:
Geeks
forGeeks
A
Computer
Portal

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blockingrequest . html # iterator()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#iterator())