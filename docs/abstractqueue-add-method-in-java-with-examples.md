# Java 中的抽象队列 add()方法，带示例

> 原文:[https://www . geesforgeks . org/abstract queue-add-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractqueue-add-method-in-java-with-examples/)

**[【抽象队列】](https://www.geeksforgeeks.org/abstractqueue-in-java-with-examples/)** 的 **add(E e)** 方法将指定的元素插入到该队列中，如果可以在不违反容量限制的情况下立即插入。成功后返回真，如果当前没有可用空间，则抛出*非法状态异常*。

**语法:**

```
public boolean add(E e)
```

**参数:**这个方法接受一个强制参数 **e** ，它是要插入到队列中的元素。

**返回:**该方法返回*真*如果元素被插入到队列中，则返回*假。*

**异常:**此方法抛出以下异常:

*   **[illegalstateexception]** : If the element cannot be added due to capacity limitation at this time.
*   [T0】 NullPointerException 【T1]: If the specified element is empty.
*   **classcasteexception** –If the class of the specified element prevents it from being added to this queue.
*   **非法论证异常**–ⅲ{ fnsegoeprintfs 201 ch 00 ffff 3 chff 0000 } illillegalyarguments exception-{ fnsegoeprintfs 201 ch 00 ffff 3 chff 0000 }

下面程序举例说明 add()方法:

**程序 1:**

```
// Java program to illustrate the
// AbstractQueue add() method
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        // Creating object of AbstractQueue<Integer>
        AbstractQueue<Integer>
            AQ = new LinkedBlockingQueue<Integer>();

        // Populating AQ
        AQ.add(10);
        AQ.add(20);
        AQ.add(30);
        AQ.add(40);
        AQ.add(50);

        // print AQ
        System.out.println("AbstractQueue contains : " + AQ);
    }
}
```

**输出:**

```
AbstractQueue contains : [10, 20, 30, 40, 50]

```

**程序 2:** 程序为*非法状态异常*

```
// Java program to illustrate the
// AbstractQueue add() method
// IllegalStateException
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        try {
            // Creating object of AbstractQueue<Integer>
            AbstractQueue<Integer>
                AQ = new LinkedBlockingQueue<Integer>(2);

            // Populating AQ
            AQ.add(10);
            AQ.add(20);
            AQ.add(30);
            AQ.add(40);
            AQ.add(50);

            // print AQ
            System.out.println("AbstractQueue contains : " + AQ);
        }
        catch (Exception e) {
            System.out.println("exception: " + e);
        }
    }
}
```

**输出:**

```
exception: java.lang.IllegalStateException: Queue full

```

**程序 3:** 程序为*空指针异常*

```
// Java program to illustrate the
// AbstractQueue add() method
// NullPointerException
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        try {
            // Creating object of AbstractQueue<Integer>
            AbstractQueue<Integer>
                AQ = new LinkedBlockingQueue<Integer>();

            // Populating AQ
            AQ.add(10);
            AQ.add(20);
            AQ.add(30);
            AQ.add(null);
            AQ.add(50);

            // print AQ
            System.out.println("AbstractQueue contains : " + AQ);
        }
        catch (Exception e) {
            System.out.println("exception: " + e);
        }
    }
}
```

**输出:**

```
exception: java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/abstractqueue . html # add-E-](https://docs.oracle.com/javase/8/docs/api/java/util/AbstractQueue.html#add-E-)