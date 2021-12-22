# Java 中的 ConcurrentLinkedDeque remove()方法，示例

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-remove-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentlinkeddeque-remove-method-in-java-with-examples/)

[T1](https://www.geeksforgeeks.org/concurrentlinkeddeque-in-java-with-examples/)T4。remove() 是 Java 中的一个内置函数，用于从这个 deque 中移除一个元素。
**语法:**

```
public E remove()
        or
public boolean remove(Object o)
```

**参数:**该方法第一次重载**不接受**任何参数。然而，这个方法的第二个重载接受一个元素的**作为参数，该参数将从这个 concurrentlinkedrequest 中移除。
**返回值:**如果没有指定特定的元素作为参数，该方法返回被移除的**元素**。如果一个元素被指定为参数，那么它返回一个**布尔值**，说明这个元素是否被移除。
**异常:**该函数的第一次重载，如果这个 deque 为空，抛出 **NoSuchElementException** 。而如果指定的元素为空，第二个重载抛出**空指针异常**。
以下程序说明了 ConcurrentLinkedDeque.remove()方法:
**示例:1**** 

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate
// ConcurrentLinkedDeque remove() method

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {

        // Create a ConcurrentLinkedDeque
        // using ConcurrentLinkedDeque() constructor
        ConcurrentLinkedDeque<Integer>
            cld = new ConcurrentLinkedDeque<Integer>();

        cld.add(40);
        cld.add(50);
        cld.add(60);
        cld.add(70);
        cld.add(80);

        // Displaying the existing LinkedDeque
        System.out.println("Existing ConcurrentLinkedDeque: "
                           + cld);

        // remove method removes the first element of queue
        // using remove() method
        System.out.println("Element removed: "
                           + cld.remove());

        // Displaying the existing LinkedDeque
        System.out.println("Modified ConcurrentLinkedDeque: "
                           + cld);
    }
}
```

**Output:** 

```
Existing ConcurrentLinkedDeque: [40, 50, 60, 70, 80]
Element removed: 40
Modified ConcurrentLinkedDeque: [50, 60, 70, 80]
```

**例:2**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate
// ConcurrentLinkedDeque remove(Object o) method

import java.util.concurrent.*;

class ConcurrentLinkedDequeDemo {
    public static void main(String[] args)
    {
        ConcurrentLinkedDeque<String> cld
            = new ConcurrentLinkedDeque<String>();

        cld.add("GFG");
        cld.add("Gfg");
        cld.add("GeeksforGeeks");
        cld.add("Geeks");

        // Displaying the existing LinkedDeque
        System.out.println("Elements in"
                           + "the LinkedDeque: " + cld);

        // Remove "Gfg" using remove(Object)
        System.out.println("Gfg removed: "
                           + cld.remove("Gfg"));

        // Displaying the elements
        System.out.println("Elements in"
                           + "the LinkedDeque: " + cld);
    }
}
```

**Output:** 

```
Elements inthe LinkedDeque: [GFG, Gfg, GeeksforGeeks, Geeks]
Gfg removed: true
Elements inthe LinkedDeque: [GFG, GeeksforGeeks, Geeks]
```