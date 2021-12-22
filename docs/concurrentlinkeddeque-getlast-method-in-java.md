# Java 中的 concurrentlinkedequegetlast()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-get last-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkeddeque-getlast-method-in-java/)

**java . util . concurrentlinkeDequest . getlast()**方法是 Java 中的内置方法，它返回 deque 容器的最后一个元素。

**语法:**

```
Conn_Linked_Deque.getLast()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回德格中存在的最后一个元素。

**异常:**当德格为空时，函数抛出[*no suchelementexception*](https://docs.oracle.com/javase/8/docs/api/java/util/NoSuchElementException.html)。

下面的程序说明了**concurrentlinkedequetlast()**方法:

**程序 1** :

```
/* Java Program to Demonstrate getLast()
   method of ConcurrentLinkedDeque */

import java.util.concurrent.*;
class GFG {
    public static void main(String[] args)
    {

        // Creating an empty Deque
        ConcurrentLinkedDeque<String> cld = new ConcurrentLinkedDeque<String>();

        // Add elements into the Deque
        cld.add("Welcome");
        cld.add("To");
        cld.add("Geeks");
        cld.add("4");
        cld.add("Geeks");

        // Displaying the Deque
        System.out.println("Elements in Deque: " + cld);

        // Displaying the Last element
        System.out.println("The Last element is: " + cld.getLast());
    }
}
```

**输出:**

```
Elements in Deque: [Welcome, To, Geeks, 4, Geeks]
The Last element is: Geeks

```

**程序二:**

```
/* Java Program to Demonstrate getLast()
   method of ConcurrentLinkedDeque */

import java.util.concurrent.*;
class GFG {
    public static void main(String[] args)
    {

        // Creating an empty Deque
        ConcurrentLinkedDeque<Integer> cld = new ConcurrentLinkedDeque<Integer>();

        try {
            // Displaying the Last element
            System.out.println("The Last element "
                               + "is: " + cld.getLast());
        }
        catch (Exception e) {
            // Displaying the Exception
            System.out.println(e);
        }

        // Add elements into the Deque
        cld.add(12);
        cld.add(43);
        cld.add(29);
        cld.add(16);
        cld.add(70);

        // Displaying the Deque
        System.out.println("Elements in "
                           + "Deque: " + cld);

        // Displaying the Last element
        System.out.println("The Last element is: " + cld.getLast());
    }
}
```

**输出:**

```
java.util.NoSuchElementException
Elements in Deque: [12, 43, 29, 16, 70]
The Last element is: 70

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentlinkedeque . html # getLast()](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#getLast--)