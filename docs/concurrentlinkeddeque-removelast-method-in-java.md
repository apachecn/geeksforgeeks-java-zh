# Java 中的 concurrentlinkedrequeremovelast()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-remove last-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkeddeque-removelast-method-in-java/)

**concurrentlinkedrequest . removelast()**是 Java 中的内置函数，它删除了 deque 中的最后一个元素。如果*这个*德格是空的，函数抛出 *NoSuchElementException* 。

**语法:**

```java
Conn_Linked_Deque.removeLast()
```

**参数:**函数不接受任何参数。

**返回值:**该函数返回 deque 中的最后一个元素。

**异常:**如果*这个*德格为空，函数抛出 *NoSuchElementException* 。

下面的程序说明了 removeLast()方法:

**程序 1:** 该程序涉及带有*整数*元素的德格。

```java
// Java Program Demonstrate removeLast() 
// method of ConcurrentLinkedDeque   

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        ConcurrentLinkedDeque<Integer> cld = 
                      new ConcurrentLinkedDeque<Integer>();

        cld.addFirst(12);
        cld.addFirst(70);
        cld.addFirst(1009);
        cld.addFirst(475);

        // Displaying the existing LinkedDeque
        System.out.println("Elements in"
                           + "the LinkedDeque: " + cld);

        // Display the last element
        System.out.println("Element removed : "
                           + cld.peekLast());

        // Remove the Last element
        cld.removeLast();

        // Displaying the elements
        System.out.println("Elements in"
                           + "the LinkedDeque: " + cld);
    }
}
```

**输出:**

```java
Elements inthe LinkedDeque: [475, 1009, 70, 12]
Element removed : 12
Elements inthe LinkedDeque: [475, 1009, 70]

```

**节目 2:** 这个节目涉及到带有*弦*元素的德格。

```java
// Java Program Demonstrate removeLast() 
// method of ConcurrentLinkedDeque   

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        ConcurrentLinkedDeque<String> cld = 
                           new ConcurrentLinkedDeque<String>();

        cld.addFirst("GFG");
        cld.addFirst("Gfg");
        cld.addFirst("GeeksforGeeks");
        cld.addFirst("Geeks");

        // Displaying the existing LinkedDeque
        System.out.println("Elements in"
                           + "the LinkedDeque: " + cld);

        // Display the last element
        System.out.println("Element removed : "
                           + cld.peekLast());

        // Remove the Last element
        cld.removeLast();

        // Displaying the elements
        System.out.println("Elements in"
                           + "the LinkedDeque: " + cld);
    }
}
```

**输出:**

```java
Elements inthe LinkedDeque: [Geeks, GeeksforGeeks, Gfg, GFG]
Element removed : GFG
Elements inthe LinkedDeque: [Geeks, GeeksforGeeks, Gfg]

```

**参考**:[https://docs . Oracle . com/javae/8/docs/API/Java/util/concurrent/concurrent ked dequake . html # remove last()](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#removeLast--)