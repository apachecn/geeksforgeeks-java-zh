# 用示例链接 Java 中的锁请求 forEach()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-foreach-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedblockingdeque-foreach-method-in-java-with-examples/)

[link edblockingrequest](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)的 **forEach()** 方法为 Iterable 的每个元素执行给定的操作，直到所有元素都被处理完或者该操作抛出异常。

**语法:**

```
public void forEach(Consumer<E> action)

```

**参数:**该方法采用一个参数动作，代表每个元素要执行的动作。

**返回值:**这个方法不返回任何东西。

**异常:**如果指定的动作为空，该方法抛出**空指针异常**。

下面的程序说明了 LinkedBlockingDeque 类的 forEach()函数:

**例:**

```
// Java Program Demonstrate forEach()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add(11);
        LBD.add(22);
        LBD.add(33);
        LBD.add(44);
        LBD.add(55);
        LBD.add(66);
        LBD.add(77);

        // print deque
        System.out.println("Linked Blocking Deque: "
                           + LBD);

        System.out.println("Traversing this Deque: ");

        // Traverse this queue using forEach() method
        LBD.forEach((n) -> System.out.println(n));
    }
}
```

**输出:**

```
Linked Blocking Deque: [11, 22, 33, 44, 55, 66, 77]
Traversing this Deque: 
11
22
33
44
55
66
77

```

**示例:2**

```
// Java Program Demonstrate forEach()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<String> LBD
            = new LinkedBlockingDeque<String>();

        // Add elements to end of LinkedBlockingDeque
        LBD.add("GeeksforGeeks");
        LBD.add("Gfg");
        LBD.add("Geeks");
        LBD.add("Computer");
        LBD.add("Science");
        LBD.add("Portal");

        // print deque
        System.out.println("Linked Blocking Deque: "
                           + LBD);

        System.out.println("Traversing this deque: ");

        // Traverse this deque using forEach() method
        LBD.forEach((n) -> System.out.println(n));
    }
}
```

**输出:**

```
Linked Blocking Deque: [GeeksforGeeks, Gfg, Geeks, Computer, Science, Portal]
Traversing this deque: 
GeeksforGeeks
Gfg
Geeks
Computer
Science
Portal

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/concurrent/linkedblockingrequest . html # forEach-Java . util . function . consumer-](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/LinkedBlockingDeque.html#forEach-java.util.function.Consumer-)