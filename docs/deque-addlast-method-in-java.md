# Java 中的 Deque addLast()方法

> 原文:[https://www.geeksforgeeks.org/deque-addlast-method-in-java/](https://www.geeksforgeeks.org/deque-addlast-method-in-java/)

[德客界面](https://www.geeksforgeeks.org/deque-interface-java-example/)的 **addLast(E e)** 方法将参数中传递的元素插入到德客的末尾，如果有空间的话。如果 Deque 容量受限，并且没有空间可供插入，它将返回一个*非法状态异常*。函数在成功插入时返回 true。

**语法:**

```java
boolean addLast(E e)
```

**参数:**此方法接受一个强制参数 **e** ，它是要插入到德格末尾的元素。

**返回:**该方法在成功插入时返回 true。

**异常:**函数抛出四个异常，描述如下:

*   **classcastexception** : When the class of the element to be input prevents it from being added to this container.
*   [T0】 illegalsteexception 【T1]: When the capacity of the container is full and the insertion is completed.
*   [T0】 IllegalArgumentException 【T1]: When some attributes of an element prevent it from being added to Deque.
*   [T0】 NullPointerException 【T1]: When the element to be inserted is passed as null, and the interface of Deque does not allow null elements.

下面的程序说明了实现德客接口的各种类对 addLast()方法的*实现:*

**程序一:**借助 [**链接列表**](https://www.geeksforgeeks.org/linked-list-in-java/) 。

```java
// Java Program Demonstrate addLast()
// method of Deque

import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of De1ue
        Deque<Integer> DQ
            = new LinkedList<Integer>();

        // Add numbers to end of Deque
        DQ.addLast(7855642);
        DQ.addLast(35658786);
        DQ.addLast(5278367);
        DQ.addLast(74381793);

        // before removing print Deque
        System.out.println("Deque: " + DQ);
    }
}
```

**输出:**

```java
Deque: [7855642, 35658786, 5278367, 74381793]

```

**程序二:**在**的帮助下链接锁定程序**。

```java
// Java Program Demonstrate addLast()
// method of Deque

import java.util.*;
import java.util.concurrent.LinkedBlockingDeque;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of De1ue
        Deque<Integer> DQ
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of Deque
        DQ.addLast(7855642);
        DQ.addLast(35658786);
        DQ.addLast(5278367);
        DQ.addLast(74381793);

        // before removing print Deque
        System.out.println("Deque: " + DQ);
    }
}
```

**输出:**

```java
Deque: [7855642, 35658786, 5278367, 74381793]

```

**节目 3:** 借助 **ArrayDeque** 。

```java
// Java Program Demonstrate addLast()
// method of Deque

import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of De1ue
        Deque<Integer> DQ
            = new ArrayDeque<Integer>();

        // Add numbers to end of Deque
        DQ.addLast(7855642);
        DQ.addLast(35658786);
        DQ.addLast(5278367);
        DQ.addLast(74381793);

        // before removing print Deque
        System.out.println("Deque: " + DQ);
    }
}
```

**输出:**

```java
Deque: [7855642, 35658786, 5278367, 74381793]

```