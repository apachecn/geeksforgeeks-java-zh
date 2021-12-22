# 用示例链接 Java 中的 TransferQueue forEach()方法

> 原文:[https://www . geeksforgeeks . org/link edtransferqueue-foreach-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedtransferqueue-foreach-method-in-java-with-examples/)

[Java . util . concurrent . LinkedTransferqueue](https://www.geeksforgeeks.org/linkedtransferqueue-in-java-with-examples/)的 **forEach()** 方法是 Java 中的一个内置函数，用来遍历这个队列中的每个元素。

**语法:**

```
public void forEach(Consumer<E> action)
```

**参数:**该方法采用一个参数动作，代表每个元素要执行的动作。

**返回值:**这个方法不返回任何东西。

**异常:**如果指定的动作为空，该方法抛出**空指针异常**。

下面的程序说明了 LinkedTransferQueue 类的 forEach()函数:

**程序 1:**

```
// Java code to illustrate
// forEach() method of LinkedTransferQueue

import java.util.concurrent.LinkedTransferQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // Create object of LinkedTransferQueue
        LinkedTransferQueue<Integer> LTQ
            = new LinkedTransferQueue<Integer>();

        // Add numbers to end of LinkedTransferQueue
        // using add() method
        LTQ.add(6);
        LTQ.add(3);
        LTQ.add(5);
        LTQ.add(15);
        LTQ.add(20);

        // Prints the Deque
        System.out.println("Linked Transfer Queue : "
                           + LTQ);

        System.out.println("Traversing this Queue : ");

        // Traverse this queue using forEach() method
        LTQ.forEach((n) -> System.out.println(n));
    }
}
```

**输出:**

```
Linked Transfer Queue : [6, 3, 5, 15, 20]
Traversing this Queue : 
6
3
5
15
20

```

**程序二:**

```
// Java code to illustrate
// forEach() method of LinkedTransferQueue

import java.util.concurrent.LinkedTransferQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // Create object of LinkedTransferQueue
        LinkedTransferQueue<String> LTQ
            = new LinkedTransferQueue<String>();

        // Add numbers to end of LinkedTransferQueue
        // using add() method
        LTQ.add("GeeksforGeeks");
        LTQ.add("Geeks");
        LTQ.add("Computer Science");
        LTQ.add("Portal");
        LTQ.add("Gfg");

        // Prints the Deque
        System.out.println("Linked Transfer Queue : "
                           + LTQ);
        System.out.println("Traversing this Queue : ");

        // Traverse this queue using forEach() method
        LTQ.forEach((n) -> System.out.println(n));
    }
}
```

**输出:**

```
Linked Transfer Queue : [GeeksforGeeks, Geeks, Computer Science, Portal, Gfg]
Traversing this Queue : 
GeeksforGeeks
Geeks
Computer Science
Portal
Gfg

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/concurrent/linkedtransferqueue . html # forEach-Java . util . function . consumer-](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/LinkedTransferQueue.html#forEach-java.util.function.Consumer-)