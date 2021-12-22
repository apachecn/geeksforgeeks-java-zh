# Java 中的 concurrentlinkedeque removelastpocent()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-removelastpoccurrence-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkeddeque-removelastoccurrence-method-in-java/)

**java . util . concurrentlinkeDeque . removelastpoccurrence()**方法是 Java 中的一个内置方法，它接受一个参数，并删除该元素在 deque 中的最后一次出现。因此，在元素不存在于 deque 中的情况下，它保持不变。

**语法:**

```
public boolean removeLastOccurrence(Object o)
```

**参数:**该函数接受一个对象 **elem** 作为参数，该参数表示其最后一次出现在图像中的对象将被删除。

**返回值:**如果 edeque 中存在 **elem** ，则函数返回 *true* ，否则返回 *false* 。

**异常:**如果作为参数传递给函数的指定元素为空，函数将抛出*空指针异常*。

下面的程序举例说明了**removelastcessence()**方法的使用:

```
/* Java program to demonstrate 
   removeLastOccurrence() method
   of ConcurrentLinkedDeque   */

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        ConcurrentLinkedDeque<String> cld = new ConcurrentLinkedDeque<String>();

        cld.addFirst("GFG");
        cld.addFirst("Geeks");
        cld.addFirst("Gfg");
        cld.addFirst("gfg");
        cld.addFirst("Geeks");

        // Displaying the existing LinkedDeque
        System.out.println("Elements in "
                           + "the LinkedDeque: " + cld);

        // Remove last occurrence of  element
        cld.removeLastOccurrence("Geeks");

        // Displaying the modified LinkedDeque
        System.out.println("Elements in "
                           + "the LinkedDeque: " + cld);
    }
}
```

**输出:**

```
Elements in the LinkedDeque: [Geeks, gfg, Gfg, Geeks, GFG]
Elements in the LinkedDeque: [Geeks, gfg, Gfg, GFG]

```

**程序二:**

```
/* Java program to demonstrate 
   removeLastOccurrence() method
   of ConcurrentLinkedDeque   */

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        ConcurrentLinkedDeque<Integer>
            cld = new ConcurrentLinkedDeque<Integer>();

        cld.addFirst(12);
        cld.addFirst(280);
        cld.addFirst(1008);
        cld.addFirst(1050);
        cld.addFirst(379);

        // Displaying the existing LinkedDeque
        System.out.println("Elements in "
                           + "the LinkedDeque: " + cld);
        try {
            // Remove last occurrence of  element
            cld.removeLastOccurrence(null);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
Elements in the LinkedDeque: [379, 1050, 1008, 280, 12]
java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentlinkedeque . html # removelastpoccurrency()](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#removeLastOccurrence-java.lang.Object-)