# Java 中 LinkedBlockingDeque 元素()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-element-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-element-method-in-java/)

**链接锁定请求**的**元素()**方法返回容器前面的元素。它不会删除容器中的元素。这个方法返回由这个 deque 表示的队列头。

**语法:**

```
public void element()

```

**参数:**此方法不接受任何参数。

**返回:**这个方法返回这个 deque 所代表的队列头。

下面的程序说明了 link edblockingrequest 的 element()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate element()
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
        LBD.add(10);
        LBD.add(20);
        LBD.add(30);
        LBD.add(40);

        // before removing print queue
        System.out.println("Linked Blocking Deque: " + LBD);

        System.out.println("Linked Blocking Deque front element: " +
                                                     LBD.element());
    }
}
```

**Output:** 

```
Linked Blocking Deque: [10, 20, 30, 40]
Linked Blocking Deque front element: 10

```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate element()
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

        // Add numbers to end of LinkedBlockingDeque
        LBD.add("ab");
        LBD.add("cd");
        LBD.add("fg");
        LBD.add("xz");

        // before removing print queue
        System.out.println("Linked Blocking Deque: " + LBD);

        System.out.println("Linked Blocking Deque front element: " +
                                                     LBD.element());
    }
}
```

**Output:** 

```
Linked Blocking Deque: [ab, cd, fg, xz]
Linked Blocking Deque front element: ab

```

**参考:**T2【https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedblockingrequest . html # element()T4】