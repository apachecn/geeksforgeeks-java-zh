# Java 中 BlockingDeque 元素()方法，带示例

> 原文:[https://www . geeksforgeeks . org/blocking eque-element-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-element-method-in-java-with-examples/)

**阻塞请求**的**元素()**方法返回容器前面的元素。它不会删除容器中的元素。这个方法返回由这个 deque 表示的队列头。

**语法:**

```
public void element()
```

**参数:**此方法不接受任何参数。

**返回:**这个方法返回这个 deque 所代表的队列头。

**注**:**blocking eque**的 element()方法继承了 Java 中的[link edblocking eque](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类。

下面的程序说明了阻塞请求的元素()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate element()
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
        BD.add(10);
        BD.add(20);
        BD.add(30);
        BD.add(40);

        // before removing print Deque
        System.out.println("Blocking Deque: " + BD);

        System.out.println("Blocking Deque front element: " + BD.element());
    }
}
```

**Output:** 

```
Blocking Deque: [10, 20, 30, 40]
Blocking Deque front element: 10
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate element()
// method of BlockingDeque
import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;
import java.util.concurrent.BlockingDeque;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingDeque
        BlockingDeque<String> BD
            = new LinkedBlockingDeque<String>();

        // Add numbers to end of BlockingDeque
        BD.add("ab");
        BD.add("cd");
        BD.add("fg");
        BD.add("xz");

        // before removing print Deque
        System.out.println("Blocking Deque: " + BD);

        System.out.println("Blocking Deque front element: " + BD.element());
    }
}
```

**Output:** 

```
Blocking Deque: [ab, cd, fg, xz]
Blocking Deque front element: ab
```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blockingdequee . html # element()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingDeque.html#element())