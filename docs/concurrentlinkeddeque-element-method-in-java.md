# Java 中的 ConcurrentLinkedDeque 元素()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-element-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkeddeque-element-method-in-java/)

[T1](https://www.geeksforgeeks.org/concurrentlinkeddeque-in-java-with-examples/)T4。element() 是 java 中的内置函数，它检索但不移除由 deque 表示的队列头，即 deque 的第一个元素。
**语法:**

```java
conn_linked_deque.element()
```

**参数:**该方法没有参数。
**返回值:**此方法返回德格中的**第一个元素**。
**异常:**如果德格为空，此方法会抛出**nosucheelementexception**。
以下程序说明了 ConcurrentLinkedDeque . element()方法:
**程序 1:** 该程序涉及一个整数类型的 concurrentlinkedrequest。

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java example illustrating
// ConcurrentLinkedDeque element() method

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {

        // Create a ConcurrentLinkedDeque
        // using ConcurrentLinkedDeque() constructor
        ConcurrentLinkedDeque<Integer>
            cld = new ConcurrentLinkedDeque<Integer>();

        cld.add(12);
        cld.add(70);
        cld.add(1009);
        cld.add(475);

        // Displaying the existing LinkedDeque
        System.out.println("ConcurrentLinkedDeque: "
                           + cld);

        // Displaying the head of deque
        System.out.println("The Head of deque is: "
                           + cld.element());
    }
}
```

**Output:** 

```java
ConcurrentLinkedDeque: [12, 70, 1009, 475]
The Head of deque is: 12
```

**程序 2:** 该程序涉及一个字符串类型的并发链接请求。

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java example illustrating
// ConcurrentLinkedDeque element() method

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {

        // Create a ConcurrentLinkedDeque
        // using ConcurrentLinkedDeque() constructor
        ConcurrentLinkedDeque<String>
            cld = new ConcurrentLinkedDeque<String>();

        cld.add("Gfg");
        cld.add("Geeks");
        cld.add("Programming");
        cld.add("contribute");

        // Displaying the existing LinkedDeque
        System.out.println("ConcurrentLinkedDeque: "
                           + cld);

        // Displaying the head of deque
        System.out.println("The Head of deque is: "
                           + cld.element());
    }
}
```

**Output:** 

```java
ConcurrentLinkedDeque: [Gfg, Geeks, Programming, contribute]
The Head of deque is: Gfg
```