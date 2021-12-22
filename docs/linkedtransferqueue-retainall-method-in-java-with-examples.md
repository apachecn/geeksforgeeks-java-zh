# 用示例链接 Java 中的 LinkedTransferQueue retainAll()方法

> 原文:[https://www . geeksforgeeks . org/linkedtransferqueue-retainnal-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedtransferqueue-retainall-method-in-java-with-examples/)

[java . util . concurrent . linkedtransferqueue](https://www.geeksforgeeks.org/linkedtransferqueue-in-java-with-examples/)的 **retainAll()** 方法是 Java 中的一个内置函数，用于保留该队列中指定集合和该队列共有的所有元素。所有其他不常见的元素都将从该队列中删除。

**语法:**

```
public boolean retainAll(Collection C)

```

**参数:**该方法取参数 *C* ，它是包含要保留在队列中的元素的集合。

**返回:**如果调用 else 导致队列发生变化，则该方法返回布尔值 true，否则返回 false。

**异常:**此方法抛出以下异常:

*   **ClasscasteException** : If the class of an element of this queue is incompatible with the Passed collection.
*   **Null pointer exception** : If the specified set is empty.

下面的程序说明了 LinkedTransferQueue 类的 retainAll()函数:

**程序 1:**

```
// Java code to illustrate
// retainAll() method of LinkedTransferQueue

import java.util.concurrent.LinkedTransferQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of LinkedTransferQueue
        LinkedTransferQueue<Integer> LTQ
            = new LinkedTransferQueue<Integer>();

        // Add numbers to end of LinkedTransferQueue
        // using add() method
        LTQ.add(3);
        LTQ.add(6);
        LTQ.add(10);
        LTQ.add(125);
        LTQ.add(205);

        // Print the Queue
        System.out.println("Linked Transfer Queue : "
                           + LTQ);

        // Get the ArrayList to be retained
        ArrayList<Integer> arraylist
            = new ArrayList<Integer>();
        arraylist.add(10);
        arraylist.add(100);
        arraylist.add(125);

        // Print ArrayList
        System.out.println("ArrayList to be retained : "
                           + arraylist);

        // Retaining elements from the queue
        // which are common to arraylist
        // using retainAll() method.
        LTQ.retainAll(arraylist);

        // Prints the Queue
        System.out.println("Linked Transfer Queue "
                           + "after retaining ArrayList : "
                           + LTQ);
    }
}
```

**输出:**

```
Linked Transfer Queue : [3, 6, 10, 125, 205]
ArrayList to be retained : [10, 100, 125]
Linked Transfer Queue after retaining ArrayList : [10, 125]

```

**程序二:**

```
// Java code to illustrate
// retainAll() method of LinkedTransferQueue

import java.util.concurrent.LinkedTransferQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of LinkedTransferQueue
        LinkedTransferQueue<String> LTQ
            = new LinkedTransferQueue<String>();

        // Add numbers to end of LinkedTransferQueue
        // using add() method
        LTQ.add("GeeksforGeeks");
        LTQ.add("Geek");
        LTQ.add("Gfg");
        LTQ.add("Computer");
        LTQ.add("Science");

        // Print the Queue
        System.out.println("Linked Transfer Queue : "
                           + LTQ);

        // Get the ArrayList to be retained
        ArrayList<String> arraylist
            = new ArrayList<String>();
        arraylist.add("Gfg");
        arraylist.add("Science");
        arraylist.add("Computer");

        // Print ArrayList
        System.out.println("ArrayList to be retained : "
                           + arraylist);

        // Retaining elements from the queue
        // which are common to arraylist
        // using retainAll() method.
        LTQ.retainAll(arraylist);

        // Prints the Queue
        System.out.println("Linked Transfer Queue "
                           + "after retaining ArrayList : "
                           + LTQ);
    }
}
```

**输出:**

```
Linked Transfer Queue : [GeeksforGeeks, Geek, Gfg, Computer, Science]
ArrayList to be retained : [Gfg, Science, Computer]
Linked Transfer Queue after retaining ArrayList : [Gfg, Computer, Science]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/concurrent/linkedtransferqueue . html # retailnall-Java . util . collection-](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/LinkedTransferQueue.html#retainAll-java.util.Collection-)