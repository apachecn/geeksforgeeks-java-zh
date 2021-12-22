# Java 中 LinkedTransferQueue removeIf()方法，示例

> 原文:[https://www . geeksforgeeks . org/link edtransferqueue-remove if-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedtransferqueue-removeif-method-in-java-with-examples/)

[java . util . concurrent . linkedtransferqueue](https://www.geeksforgeeks.org/linkedtransferqueue-in-java-with-examples/)的 **removeIf()** 方法是一个内置函数，它是 Java，用于移除该队列中满足给定谓词过滤器的所有元素，该谓词过滤器作为参数传递给该方法。

**语法:**

```
public boolean removeIf(Predicate filter)

```

**参数:**该方法采用参数过滤器，该过滤器表示[谓词](https://www.geeksforgeeks.org/java-8-predicate-with-examples/)，该谓词定义了要移除的元素的过滤标准。

**返回值:**该方法返回一个布尔值，描述指定元素是否被移除。如果谓词返回真并且元素已被移除，则返回真。

**异常:**如果指定的过滤器为空，该方法抛出**空指针异常**。

下面的程序说明了 LinkedTransferQueue 类的 removeIf()函数:

**程序 1:**

```
// Java code to illustrate
// removeIf() method of LinkedTransferQueue

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
        LTQ.add(6);
        LTQ.add(3);
        LTQ.add(5);
        LTQ.add(15);
        LTQ.add(20);

        // Print the LTQ
        System.out.println("Linked Transfer Queue initially: "
                           + LTQ);

        // Remove all multiple of 3
        // using removeIf() method
        if (LTQ.removeIf(n -> (n % 3 == 0)))
            System.out.println("Multiples of 3 removed.");
        else
            System.out.println("No element removed.");

        // Print the LTQ
        System.out.println("Current Linked Transfer Queue: "
                           + LTQ);
    }
}
```

**输出:**

```
Linked Transfer Queue initially: [6, 3, 5, 15, 20]
Multiples of 3 removed.
Current Linked Transfer Queue: [5, 20]

```

**程序 2:** 演示 NullPointerException

```
// Java code to illustrate
// removeIf() method of LinkedTransferQueue

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
        LTQ.add(6);
        LTQ.add(3);
        LTQ.add(5);
        LTQ.add(15);
        LTQ.add(20);

        // Print the LTQ
        System.out.println("Linked Transfer Queue initially: "
                           + LTQ);

        try {
            // Remove all multiple of 3
            // using removeIf() method
            System.out.println("Trying to remove null.");
            LTQ.removeIf(null);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
Linked Transfer Queue initially: [6, 3, 5, 15, 20]
Trying to remove null.
java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/en/Java/javase/11/docs/API/Java . base/Java/util/concurrent/linkedtransferqueue . html # removeIf(Java . util . function . prediction)](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/concurrent/LinkedTransferQueue.html#removeIf(java.util.function.Predicate))