# Java 中的 concurrentlinkedrequeremovefirst()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-remove first-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkeddeque-removefirst-method-in-java/)

concurrentlinkeDeque . removefirst()是 Java 中的内置函数，它从 deque 容器中移除第一个元素。如果*这个*德格为空，函数抛出 *NoSuchElementException* 。

**语法:**

```java
Conn_Linked_Deque.removeFirst()
```

**参数:**函数不接受任何参数。

**返回值:**该函数返回 deque 中的第一个元素。

**异常:**如果*这个*德格为空，函数抛出 *NoSuchElementException* 。

下面的程序说明了 removeFirst()方法:

**程序 1:** 该程序涉及带有*整数*元素的德格。

```java
// Java Program to demonstrate removeFirst() 
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

        // Display the first element
        System.out.println("Element removed : "
                           + cld.peekFirst());

        // Remove the first element
        cld.removeFirst();

        // Displaying the elements
        System.out.println("Elements in"
                           + "the LinkedDeque: " + cld);
    }
}
```

**输出:**

```java
Elements inthe LinkedDeque: [475, 1009, 70, 12]
Element removed : 475
Elements inthe LinkedDeque: [1009, 70, 12]

```

**节目 2:** 这个节目涉及到带有*弦*元素的德格。

```java
// Java Program Demonstrate removeFirst() 
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

        // Display the first element
        System.out.println("Element removed : "
                           + cld.peekFirst());

        // Remove the first element
        cld.removeFirst();

        // Displaying the elements
        System.out.println("Elements in"
                           + "the LinkedDeque: " + cld);
    }
}
```

**输出:**

```java
Elements inthe LinkedDeque: [Geeks, GeeksforGeeks, Gfg, GFG]
Element removed : Geeks
Elements inthe LinkedDeque: [GeeksforGeeks, Gfg, GFG]

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentlinkedeque . html # removeFirst()](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#removeFirst--)