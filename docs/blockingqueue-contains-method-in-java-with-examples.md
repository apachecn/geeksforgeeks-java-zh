# BlockingQueue 包含 Java 中的()方法，并附有示例

> 原文:[https://www . geesforgeks . org/blockingqueue-contains-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingqueue-contains-method-in-java-with-examples/)

**包含**阻塞队列**接口的(对象 o)** 方法，检查参数中传递的元素在容器中是否存在。如果元素存在于容器中，则返回 true，否则返回 false 值。

**语法:**

```
public boolean contains(Object o)
```

**参数:**该方法接受一个强制参数 **o** ，其在容器中的存在将在容器中被检查。

**返回:**如果元素存在，这个方法返回真，否则返回假。

**注**:**包含()**封锁队列**的**方法继承了 Java 中的**队列**类。

下面的程序说明了包含()方法的阻塞队列:

**程序 1:**

```
// Java Program Demonstrate contains()
// method of BlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingQueue
        BlockingQueue<Integer> BQ
            = new LinkedBlockingQueue<Integer>();

        // Add numbers to end of BlockingQueue
        BQ.add(10);
        BQ.add(20);
        BQ.add(30);
        BQ.add(40);

        // before removing print queue
        System.out.println("Blocking Queue: " + BQ);

        // check for presence using function
        if (BQ.contains(10)) {
            System.out.println("Blocking Queue contains 10");
        }
        else {
            System.out.println("Blocking Queue does not contain 10");
        }
    }
}
```

**输出:**

```
Blocking Queue: [10, 20, 30, 40]
Blocking Queue contains 10

```

**程序二:**

```
// Java Program Demonstrate contains()
// method of BlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingQueue
        BlockingQueue<String> BQ
            = new LinkedBlockingQueue<String>();

        // Add numbers to end of BlockingQueue
        BQ.add("ab");
        BQ.add("cd");
        BQ.add("fg");
        BQ.add("xz");

        // before removing print queue
        System.out.println("Blocking Queue: " + BQ);

        // check for presence using function
        if (BQ.contains("go")) {
            System.out.println("Blocking Queue contains 'go'");
        }
        else {
            System.out.println("Blocking Queue does not contain 'go'");
        }
    }
}
```

**输出:**

```
Blocking Queue: [ab, cd, fg, xz]
Blocking Queue does not contain 'go'

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedblockingqueue . html # contains(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingQueue.html#contains(java.lang.Object))