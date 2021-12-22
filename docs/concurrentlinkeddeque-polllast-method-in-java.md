# Java 中的 concurrentlinkedequepollast()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-poll last-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkeddeque-polllast-method-in-java/)

**java . util . concurrentlinkedequest . pollast()**是 Java 中的一个内置方法，它检索这个 deque 的最后一个元素*并将其移除。如果目的地为空，则该方法返回*空值*。*

**语法:**

```
Conn_Linked_Deque.pollLast()
```

**参数:**函数不接受参数。

**返回值:**函数返回*这个*的最后一个元素。如果*这个*德格为空，则该功能返回*空*。

下面的程序说明了 pollFirst()方法的使用:

**程序 1:** 该程序涉及带有*整数*元素的德格。

```
/* Java Program Demonstrate pollLast() 
 method of ConcurrentLinkedDeque   */

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

        // Display and remove the Last element
        System.out.println("Element removed : "
                           + cld.pollLast());

        // Displaying the elements
        System.out.println("Elements in"
                           + "the LinkedDeque: " + cld);
    }
}
```

**输出:**

```
Elements inthe LinkedDeque: [475, 1009, 70, 12]
Element removed : 12
Elements inthe LinkedDeque: [475, 1009, 70]

```

**节目 2:** 这个节目涉及到带有*弦*元素的德格。

```
/* Java Program Demonstrate pollLast() 
 method of ConcurrentLinkedDeque   */

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        ConcurrentLinkedDeque<String> cld = 
                       new ConcurrentLinkedDeque<String>();

        cld.addFirst("GFG");
        cld.addFirst("Geeks");
        cld.addFirst("Gfg");
        cld.addFirst("Geeks");

        // Displaying the existing LinkedDeque
        System.out.println("Elements in"
                           + "the LinkedDeque: " + cld);

        // Display and remove the Last element
        System.out.println("Element removed : "
                           + cld.pollLast());

        // Displaying the elements
        System.out.println("Elements in"
                           + "the LinkedDeque: " + cld);
    }
}
```

**输出:**

```
Elements inthe LinkedDeque: [Geeks, Gfg, Geeks, GFG]
Element removed : GFG
Elements inthe LinkedDeque: [Geeks, Gfg, Geeks]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentlinkedeque . html # pollast()](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#pollLast--)