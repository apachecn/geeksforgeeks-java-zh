# Java 中的 Deque add()方法

> 原文:[https://www.geeksforgeeks.org/deque-add-method-in-java/](https://www.geeksforgeeks.org/deque-add-method-in-java/)

[得克接口](https://www.geeksforgeeks.org/deque-interface-java-example/)的 **add(E e)** 方法，如果有空间，将参数中传递的元素插入到得克的末尾。如果 Deque 容量受限，并且没有空间可供插入，它将返回一个*非法状态异常*。函数在成功插入时返回 true。

**语法:**

```java
boolean add(E e)

```

**参数:**此方法接受一个强制参数 **e** ，它是要插入到德格末尾的元素。

**返回:**该方法在成功插入时返回 true。

**异常:**函数抛出四个异常，描述如下:

*   **classcastexception** : When the class of the element to be input prevents it from being added to this container.
*   [T0】 illegalsteexception 【T1]: When the capacity of the container is full and the insertion is completed.
*   [T0】 IllegalArgumentException 【T1]: When some attributes of an element prevent it from being added to Deque.
*   [T0】 NullPointerException 【T1]: When the element to be inserted is passed as null, and the interface of Deque does not allow null elements.

下面的程序说明了添加()的方法:

**程序一:**借助 [**链接列表**](https://www.geeksforgeeks.org/linked-list-in-java/) 。

## Java

```java
// Java Program Demonstrate add()
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
        DQ.add(7855642);
        DQ.add(35658786);
        DQ.add(5278367);
        DQ.add(74381793);

        // before removing print Deque
        System.out.println("Deque: " + DQ);
    }
}
```

**输出:**

```java
Deque: [7855642, 35658786, 5278367, 74381793]

```

**节目 2:** 借助 **ArrayDeque** 。

## Java

```java
// Java Program Demonstrate add()
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
        DQ.add(7855642);
        DQ.add(35658786);
        DQ.add(5278367);
        DQ.add(74381793);

        // before removing print Deque
        System.out.println("Deque: " + DQ);
    }
}
```

**输出:**

```java
Deque: [7855642, 35658786, 5278367, 74381793]

```

**程序 3:** 在**的帮助下**同意链接请求。

## Java

```java
// Java Program Demonstrate add()
// method of Deque
import java.util.*;
import java.util.concurrent.ConcurrentLinkedDeque;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of De1ue
        Deque<Integer> DQ
            = new ConcurrentLinkedDeque<Integer>();

        // Add numbers to end of Deque
        DQ.add(7855642);
        DQ.add(35658786);
        DQ.add(5278367);
        DQ.add(74381793);

        // before removing print Deque
        System.out.println("Deque: " + DQ);
    }
}
```

**输出:**

```java
Deque: [7855642, 35658786, 5278367, 74381793]

```