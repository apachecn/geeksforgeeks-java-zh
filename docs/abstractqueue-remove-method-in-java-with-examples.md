# Java 中的抽象 Queue remove()方法，示例

> 原文:[https://www . geesforgeks . org/abstract queue-remove-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractqueue-remove-method-in-java-with-examples/)

**[抽象队列](https://www.geeksforgeeks.org/abstractqueue-in-java-with-examples/)** 的 **remove()** 方法返回并移除该队列的头部。

**语法:**

```
public E remove()
```

**参数:**此方法不接受任何参数。

**返回:**该方法返回队列的**头**。

**异常:**如果队列为空，函数抛出***no suchelementexception***。

以下程序说明*移除()*的方法:

**程序 1:**

```
// Java program to illustrate the
// AbstractQueue remove() method
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        // Creating object of AbstractQueue<Integer>
        AbstractQueue<Integer>
            AQ1 = new LinkedBlockingQueue<Integer>();

        // Populating AQ1
        AQ1.add(10);
        AQ1.add(20);
        AQ1.add(30);
        AQ1.add(40);
        AQ1.add(50);

        // print AQ
        System.out.println("AbstractQueue1 contains : " + AQ1);

        // retrieves the head
        int head = AQ1.remove();
        System.out.println("head : " + head);

        // print AQ
        System.out.println("AbstractQueue1 after removal of head : " + AQ1);
    }
}
```

**输出:**

```
AbstractQueue1 contains : [10, 20, 30, 40, 50]
head : 10
AbstractQueue1 after removal of head : [20, 30, 40, 50]

```

**程序二:**

```
// Java program to illustrate the
// AbstractQueue element() method
// NoSuchElementException
// Java program to illustrate the
// AbstractQueue remove() method
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        try {
            // Creating object of AbstractQueue<Integer>
            AbstractQueue<Integer>
                AQ1 = new LinkedBlockingQueue<Integer>();

            // Populating AQ1
            AQ1.add(10);

            // print AQ
            System.out.println("AbstractQueue1 contains : " + AQ1);

            // retrieves the head
            int head = AQ1.remove();
            System.out.println("head : " + head);

            // retrieves the head again
            head = AQ1.remove();
            System.out.println("head : " + head);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```
AbstractQueue1 contains : [10]
head : 10
Exception: java.util.NoSuchElementException

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/abstractqueue . html # remove–](https://docs.oracle.com/javase/8/docs/api/java/util/AbstractQueue.html#remove--)