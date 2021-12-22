# Java 中的 Deque offerLast()方法

> 原文:[https://www . geesforgeks . org/deque-offer last-method-in-Java/](https://www.geeksforgeeks.org/deque-offerlast-method-in-java/)

**[德客界面](https://www.geeksforgeeks.org/deque-interface-java-example/)** 的 **offerLast(E e)** 方法在不违反容量限制的情况下，将指定元素插入德客的末尾。该方法优于 *add()* 方法，因为该方法在容器容量满时不会抛出异常，因为它返回 false。

**语法:**

```
boolean offerLast(E e)
```

**参数:**此方法接受一个强制参数 **e** ，它是要插入到德格末尾的元素。

**返回:**该方法在成功插入时返回真，否则返回假。

**异常:**函数抛出三个异常，描述如下:

*   **classcastexception** : When the class of the element to be input prevents it from being added to this container.
*   [T0】 IllegalArgumentException 【T1]: When some attributes of an element prevent it from being added to Deque.
*   [T0】 NullPointerException 【T1]: When the element to be inserted is passed as null, and the interface of Deque does not allow null elements.

下面的程序说明了 Deque 的 offerLast()方法:

**程序一:**借助 [**链接列表**](https://www.geeksforgeeks.org/linked-list-in-java/) 。

```
// Java Program Demonstrate offerLast()
// method of Deque when Null is passed
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new LinkedList<Integer>();

        if (DQ.offerLast(10))
            System.out.println("The Deque is not full and 10 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerLast(15))
            System.out.println("The Deque is not full and 15 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerLast(25))
            System.out.println("The Deque is not full and 25 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerLast(20))
            System.out.println("The Deque is not full and 20 is inserted");
        else
            System.out.println("The Deque is full");

        // before removing print Deque
        System.out.println("Deque: " + DQ);
    }
}
```

**输出:**

```
The Deque is not full and 10 is inserted
The Deque is not full and 15 is inserted
The Deque is not full and 25 is inserted
The Deque is not full and 20 is inserted
Deque: [10, 15, 25, 20]

```

**节目 2:** 借助 **ArrayDeque** 。

```
// Java Program Demonstrate offerLast()
// method of Deque when Null is passed
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new ArrayDeque<Integer>();

        if (DQ.offerLast(10))
            System.out.println("The Deque is not full and 10 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerLast(15))
            System.out.println("The Deque is not full and 15 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerLast(25))
            System.out.println("The Deque is not full and 25 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerLast(20))
            System.out.println("The Deque is not full and 20 is inserted");
        else
            System.out.println("The Deque is full");

        // before removing print Deque
        System.out.println("Deque: " + DQ);
    }
}
```

**输出:**

```
The Deque is not full and 10 is inserted
The Deque is not full and 15 is inserted
The Deque is not full and 25 is inserted
The Deque is not full and 20 is inserted
Deque: [10, 15, 25, 20]

```

**程序 3:** 在**的帮助下**同意链接请求。

```
// Java Program Demonstrate offerLast()
// method of Deque when Null is passed
import java.util.*;
import java.util.concurrent.ConcurrentLinkedDeque;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new ConcurrentLinkedDeque<Integer>();

        if (DQ.offerLast(10))
            System.out.println("The Deque is not full and 10 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerLast(15))
            System.out.println("The Deque is not full and 15 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerLast(25))
            System.out.println("The Deque is not full and 25 is inserted");
        else
            System.out.println("The Deque is full");

        if (DQ.offerLast(20))
            System.out.println("The Deque is not full and 20 is inserted");
        else
            System.out.println("The Deque is full");

        // before removing print Deque
        System.out.println("Deque: " + DQ);
    }
}
```

**输出:**

```
The Deque is not full and 10 is inserted
The Deque is not full and 15 is inserted
The Deque is not full and 25 is inserted
The Deque is not full and 20 is inserted
Deque: [10, 15, 25, 20]

```