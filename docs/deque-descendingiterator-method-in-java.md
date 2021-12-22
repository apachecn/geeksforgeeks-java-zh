# Java 中的 Deque descendingIterator()方法

> 原文:[https://www . geeksforgeeks . org/deque-dependingiterator-method-in-Java/](https://www.geeksforgeeks.org/deque-descendingiterator-method-in-java/)

[反求接口](https://www.geeksforgeeks.org/deque-interface-java-example/)的**下降迭代器(E e)** 方法以相反的顺序返回该反求中元素的迭代器。元素将按从最后(尾部)到第一(头部)的顺序返回。返回的迭代器是“弱一致”迭代器。

**语法:**

```java
Iterator descendingIterator()
```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个迭代器，以适当的顺序遍历这个对象中的元素

下面的程序说明了 Java 中的*dependingiterator()*方法:

**程序一:**借助 [**链接列表**](https://www.geeksforgeeks.org/linked-list-in-java/) 。

```java
// Java code to illustrate descendingIterator()
// method of Deque in Java
import java.util.*;

public class GFG {
    public static void main(String args[])
    {
        // Creating an empty Deque
        Deque<String> de_que = new LinkedList<String>();

        // Use add() method to add elements into the Queue
        de_que.add("Welcome");
        de_que.add("To");
        de_que.add("Geeks");
        de_que.add("4");
        de_que.add("Geeks");

        // Call iterator() method of deque
        Iterator iteratorVals = de_que.iterator();

        // Print elements of iterator
        // created from PriorityBlockingQueue
        System.out.println("The iterator values"
                           + " of deque are:");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

**输出:**

```java
The iterator values of deque are:
Welcome
To
Geeks
4
Geeks

```

**程序二:**

```java
// Java code to illustrate descendingIterator()
// method of Deque in Java
import java.util.*;

public class GFG {
    public static void main(String args[])
    {
        // Creating an empty Deque
        Deque<Integer> de_que = new LinkedList<Integer>();

        // Use add() method to add elements into the Queue
        de_que.add(10);
        de_que.add(15);
        de_que.add(30);
        de_que.add(20);
        de_que.add(5);

        // Call iterator() method of deque
        Iterator iteratorVals = de_que.iterator();

        // Print elements of iterator
        // created from PriorityBlockingQueue
        System.out.println("The iterator values"
                           + " of deque are:");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

**输出:**

```java
The iterator values of deque are:
10
15
30
20
5

```

**节目 3:** 借助 **ArrayDeque** 。

```java
// Java code to illustrate descendingIterator()
// method of Deque in Java
import java.util.*;

public class GFG {
    public static void main(String args[])
    {
        // Creating an empty Deque
        Deque<String> de_que = new ArrayDeque<String>();

        // Use add() method to add elements into the Queue
        de_que.add("Welcome");
        de_que.add("To");
        de_que.add("Geeks");
        de_que.add("4");
        de_que.add("Geeks");

        // Call iterator() method of deque
        Iterator iteratorVals = de_que.iterator();

        // Print elements of iterator
        // created from PriorityBlockingQueue
        System.out.println("The iterator values"
                           + " of deque are:");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

**输出:**

```java
The iterator values of deque are:
Welcome
To
Geeks
4
Geeks

```

**程序 4:** 在**的帮助下链接锁定程序**。

```java
// Java code to illustrate descendingIterator()
// method of Deque in Java
import java.util.*;
import java.util.concurrent.LinkedBlockingDeque;

public class GFG {
    public static void main(String args[])
    {
        // Creating an empty Deque
        Deque<String> de_que = new LinkedBlockingDeque<String>();

        // Use add() method to add elements into the Queue
        de_que.add("Welcome");
        de_que.add("To");
        de_que.add("Geeks");
        de_que.add("4");
        de_que.add("Geeks");

        // Call iterator() method of deque
        Iterator iteratorVals = de_que.iterator();

        // Print elements of iterator
        // created from PriorityBlockingQueue
        System.out.println("The iterator values"
                           + " of deque are:");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

**输出:**

```java
The iterator values of deque are:
Welcome
To
Geeks
4
Geeks

```

**方案五:**在**的配合下**。

```java
// Java code to illustrate descendingIterator()
// method of Deque in Java
import java.util.*;
import java.util.concurrent.ConcurrentLinkedDeque;

public class GFG {
    public static void main(String args[])
    {
        // Creating an empty Deque
        Deque<String> de_que = new ConcurrentLinkedDeque<String>();

        // Use add() method to add elements into the Queue
        de_que.add("Welcome");
        de_que.add("To");
        de_que.add("Geeks");
        de_que.add("4");
        de_que.add("Geeks");

        // Call iterator() method of deque
        Iterator iteratorVals = de_que.iterator();

        // Print elements of iterator
        // created from PriorityBlockingQueue
        System.out.println("The iterator values"
                           + " of deque are:");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

**输出:**

```java
The iterator values of deque are:
Welcome
To
Geeks
4
Geeks

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/Dequee . html # DecendingTerrar–](https://docs.oracle.com/javase/8/docs/api/java/util/Deque.html#descendingIterator--)