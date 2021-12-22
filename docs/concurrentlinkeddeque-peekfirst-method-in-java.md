# Java 中的 ConcurrentLinkedDeque peekFirst()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-peek first-in-method-Java/](https://www.geeksforgeeks.org/concurrentlinkeddeque-peekfirst-method-in-java/)

**java . util . concurrentlinkedequest . peek first()**是 Java 中的一个内置方法，
在不移除它的情况下检索这个的第一个元素*。如果目标为空，该功能返回*空*。*

**语法:**

```
Conn_Linked_Deque.peekFirst() 
```

**参数:**该功能不接受任何参数。

**返回值:**函数返回*这个*德格中出现的第一个元素，当德格为空时返回*空值*。

下面的程序说明了 peekFirst()方法:

**程序 1:** 该程序涉及到带有*整数*元素的德克尔。

```
// Java Program Demonstrate peekFirst()
// method of ConcurrentLinkedDeque

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        ConcurrentLinkedDeque<Integer> cld =
                    new ConcurrentLinkedDeque<Integer>();

        cld.addFirst(12);
        cld.addFirst(110);
        cld.addFirst(55);
        cld.addFirst(76);

        // Displaying the existing LinkedDeque
        System.out.println("Elements in"
                           + "the LinkedDeque: " + cld);

        // Displaying the first element
        System.out.println("First Element in"
                   + "the LinkedDeque: " + cld.peekFirst());
    }
}
```

**Output:**

```
Elements inthe LinkedDeque: [76, 55, 110, 12]
First Element inthe LinkedDeque: 76

```

**程序二:**本程序涉及带有*弦*元素的德格。

```
// Java Program Demonstrate peekFirst()
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

        // Displaying the First element
        System.out.println("First Element in"
                       + "the LinkedDeque: " + cld.peekFirst());
    }
}
```

**Output:**

```
Elements inthe LinkedDeque: [Geeks, GeeksforGeeks, Gfg, GFG]
First Element inthe LinkedDeque: Geeks

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentlinkedeque . html # peek first()](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#peekFirst--)