# Java 中 BlockingDeque push()方法示例

> 原文:[https://www . geeksforgeeks . org/blocking reque-push-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-push-method-in-java-with-examples/)

**阻塞请求**的**推(E e)** 方法将一个元素推送到这个目标所代表的堆栈上。如果有空间，它会将参数中传递的元素插入到 Deque 的前面。如果阻塞请求受到容量限制并且没有空间可供插入，它将返回一个*非法状态异常*。这个函数类似于 addFirst()的函数。

**语法:**

```
public void push(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到链接锁定请求前面的元素。

**注**:**blocking eque**的 push()方法继承了 Java 中的[link edblocking eque](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类。

**返回:**此方法不返回任何内容。

例外:

*   **illegalstatexception**:如果此时由于容量限制无法添加元素
*   **空指针异常**:如果指定的元素为空

下面的程序举例说明了 push()方法的阻塞请求:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate push()
// method of BlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.push(7855642);
        BD.push(35658786);
        BD.push(5278367);
        BD.push(74381793);

        // before removing print queue
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**Output:** 

```
Blocking Deque: [74381793, 5278367, 35658786, 7855642]
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate push()
// method of BlockingDeque
// when it is Full
import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingDeque
        // size of list
        BlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>(3);

        // Add numbers to end of BlockingDeque
        BD.push(7855642);
        BD.push(35658786);
        BD.push(5278367);

        // it is full
        BD.push(74381793);

        // before removing print queue
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```
Exception in thread "main" java.lang.IllegalStateException: Deque full
    at java.util.concurrent.LinkedBlockingDeque.addFirst(LinkedBlockingDeque.java:326)
    at java.util.concurrent.LinkedBlockingDeque.push(LinkedBlockingDeque.java:770)
    at GFG.main(GFG.java:24)
```

**程序 3:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate push()
// method of BlockingDeque
// when null is inserted

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.push(7855642);
        BD.push(35658786);
        BD.push(5278367);

        // NULL
        BD.push(null);

        // before removing print Deque
        System.out.println("Blocking Deque: " + BD);
    }
}
```

**输出:**

```
Exception in thread "main" java.lang.NullPointerException
    at java.util.concurrent.LinkedBlockingDeque.offerFirst(LinkedBlockingDeque.java:342)
    at java.util.concurrent.LinkedBlockingDeque.addFirst(LinkedBlockingDeque.java:325)
    at java.util.concurrent.LinkedBlockingDeque.push(LinkedBlockingDeque.java:770)
    at GFG.main(GFG.java:24)
```

**参考:**T2【https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blockingdequee . html # push(E)T4】