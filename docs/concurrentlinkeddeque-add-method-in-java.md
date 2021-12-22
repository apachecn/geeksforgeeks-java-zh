# Java 中的 ConcurrentLinkedDeque add()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-add-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkeddeque-add-method-in-java/)

**java . util . concurrentlinkedequest . add()**是 Java 中的一个内置函数，它在 deque 的末尾插入指定的元素。

**语法:**

```java
conn_linked_deque.add*(elem)*
```

**参数:**该方法只接受单个参数 **elem** ，该参数将被添加到并发链接请求的尾部。

**返回值:**函数没有返回值。

**异常:**当传递给函数的参数为 *null* 时，该方法将抛出[*null pointerexception*](https://docs.oracle.com/javase/7/docs/api/java/lang/NullPointerException.html)。由于其有界性，该方法永远不会抛出*illegalstatexception*或返回 false。

下面的程序说明了 ConcurrentLinkedDeque.add()方法:

**程序 1:** 该程序涉及一个整数类型的并发链接请求。

```java
// Java Program Demonstrate add()
// method of ConcurrentLinkedDeque 

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        ConcurrentLinkedDeque<Integer> cld = 
                     new ConcurrentLinkedDeque<Integer>();

        cld.add(12);
        cld.add(110);
        cld.add(55);
        cld.add(76);

        // Displaying the existing LinkedDeque
        System.out.println("Initial Elements in"
                           + "the LinkedDeque: " + cld);

        // Insert a new element in the  LinkedDeque
        cld.add(21);

        // Displaying the modified LinkedDeque
        System.out.println("Initial Elements in"
                           + "the LinkedDeque: " + cld);
    }
}
```

**输出:**

```java
Initial Elements inthe LinkedDeque: [12, 110, 55, 76]
Initial Elements inthe LinkedDeque: [12, 110, 55, 76, 21]

```

**程序 2:** 当*空值*作为参数传递给函数时，该程序涉及带有异常处理的字符串类型的并发链接请求。

```java
// Java Program Demonstrate add()
// method of ConcurrentLinkedDeque 

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        ConcurrentLinkedDeque<String> cld = 
                       new ConcurrentLinkedDeque<String>();

        cld.add("Gfg");
        cld.add("GFG");
        cld.add("Geeksforgeeks");
        cld.add("Contribute");

        // Displaying the existing LinkedDeque
        System.out.println("Initial Elements in"
                           + "the LinkedDeque: " + cld);

        /* Exception thrown when null 
             is passed as parameter*/
        try {
            cld.add(null);
        }
        catch (NullPointerException e) {
            System.out.println("NullPointerException"
                               + "thrown");
        }

        // Insert a new element in the  LinkedDeque
        cld.add("Geek Classes");
        // Displaying the modified LinkedDeque
        System.out.println("Initial Elements in"
                           + "the LinkedDeque: " + cld);
    }
}
```

**输出:**

```java
Initial Elements inthe LinkedDeque: [Gfg, GFG, Geeksforgeeks, Contribute]
NullPointerExceptionthrown
Initial Elements inthe LinkedDeque: [Gfg, GFG, Geeksforgeeks, Contribute, Geek Classes]

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrentlinkedeque . html # add()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#add(java.lang.Object))