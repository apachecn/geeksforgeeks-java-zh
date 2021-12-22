# Java 中的 Deque 迭代器()方法

> 原文:[https://www . geesforgeks . org/deque-iterator-method-in-Java/](https://www.geeksforgeeks.org/deque-iterator-method-in-java/)

**[德格接口](https://www.geeksforgeeks.org/deque-interface-java-example/)** 的**迭代器()**方法以适当的顺序返回这个德格中元素的迭代器。元素将按从第一个(头)到最后一个(尾)的顺序返回。返回的迭代器是“弱一致”迭代器。

**语法:**

```
Iterator iterator()
```

**参数:**该方法不接受任何参数。

**返回:**这个方法返回一个迭代器，以适当的顺序遍历这个对象中的元素。

下面的程序说明了*迭代器()的*方法:

**节目 1:** 借助 **ArrayDeque** 。

```
// Java Program Demonstrate iterator()
// method of Deque
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new ArrayDeque<Integer>();

        // Add numbers to end of Deque
        DQ.add(7855642);
        DQ.add(35658786);
        DQ.add(5278367);
        DQ.add(74381793);

        // Call iterator() method of Deque
        Iterator iteratorVals = DQ.iterator();

        // Print elements of iterator
        // created from Deque
        System.out.println("The iterator values"
                           + " of Deque are:");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

**输出:**

```
The iterator values of Deque are:
7855642
35658786
5278367
74381793

```

**程序二:**借助 [**链接列表**](https://www.geeksforgeeks.org/linked-list-in-java/) 。

```
// Java Program Demonstrate iterator()
// method of Deque
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new LinkedList<Integer>();

        // Add numbers to end of Deque
        DQ.add(7855642);
        DQ.add(35658786);
        DQ.add(5278367);
        DQ.add(74381793);

        // Call iterator() method of Deque
        Iterator iteratorVals = DQ.iterator();

        // Print elements of iterator
        // created from Deque
        System.out.println("The iterator values"
                           + " of Deque are:");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

**输出:**

```
The iterator values of Deque are:
7855642
35658786
5278367
74381793

```

**程序 3:** 在**的帮助下链接锁定程序**。

```
// Java Program Demonstrate iterator()
// method of Deque
import java.util.*;
import java.util.concurrent.LinkedBlockingDeque;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of Deque
        DQ.add(7855642);
        DQ.add(35658786);
        DQ.add(5278367);
        DQ.add(74381793);

        // Call iterator() method of Deque
        Iterator iteratorVals = DQ.iterator();

        // Print elements of iterator
        // created from Deque
        System.out.println("The iterator values"
                           + " of Deque are:");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

**输出:**

```
The iterator values of Deque are:
7855642
35658786
5278367
74381793

```

**程序 4:** 在**的配合下**。

```
// Java Program Demonstrate iterator()
// method of Deque
import java.util.*;
import java.util.concurrent.ConcurrentLinkedDeque;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new ConcurrentLinkedDeque<Integer>();

        // Add numbers to end of Deque
        DQ.add(7855642);
        DQ.add(35658786);
        DQ.add(5278367);
        DQ.add(74381793);

        // Call iterator() method of Deque
        Iterator iteratorVals = DQ.iterator();

        // Print elements of iterator
        // created from Deque
        System.out.println("The iterator values"
                           + " of Deque are:");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

**输出:**

```
The iterator values of Deque are:
7855642
35658786
5278367
74381793

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/deque . html #迭代器–](https://docs.oracle.com/javase/8/docs/api/java/util/Deque.html#iterator--)