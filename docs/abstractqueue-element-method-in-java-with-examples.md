# Java 中的抽象队列元素()方法，带示例

> 原文:[https://www . geesforgeks . org/abstract queue-element-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractqueue-element-method-in-java-with-examples/)

**[的**元素()**方法抽象队列](https://www.geeksforgeeks.org/abstractqueue-in-java-with-examples/)** 检索但不移除该队列的头。

**语法:**

```
public E element()
```

**参数:**此方法不接受任何参数。

**返回:**该方法返回队列的**头**。

**异常:**如果队列为空，函数抛出***no suchelementexception***。

以下程序说明*元素()*方法:

**程序 1:**

```
// Java program to illustrate the
// AbstractQueue element() method
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

        System.out.println("head : " + AQ1.element());
    }
}
```

**输出:**

```
AbstractQueue1 contains : [10, 20, 30, 40, 50]
head : 10

```

**程序二:**

```
// Java program to illustrate the
// AbstractQueue element() method
// NoSuchElementException
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

            System.out.println("AbstractQueue1 : " + AQ1.element());
        }
        catch (Exception e) {
            System.out.println("Exception is" + e);
        }
    }
}
```

**输出:**

```
Exception isjava.util.NoSuchElementException

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/abstractqueue . html #元素–](https://docs.oracle.com/javase/8/docs/api/java/util/AbstractQueue.html#element--)