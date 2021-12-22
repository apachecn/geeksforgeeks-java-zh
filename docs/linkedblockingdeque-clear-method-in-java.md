# Java 中 LinkedBlockingDeque clear()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-clear-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingdeque-clear-method-in-java/)

**链接锁定请求**的 **clear()** 方法删除链接锁定请求容器中存在的所有元素。调用函数后，容器变成空的。

**语法:**

```java
public void clear()
```

**参数:**该方法不接受任何参数

**返回:**这个方法不返回任何东西。

下面的程序说明了 link edblockingrequest 的 clear()方法:

**程序 1:**

```java
// Java Program Demonstrate clear()
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
        LBD.add(7855642);
        LBD.add(35658786);
        LBD.add(5278367);
        LBD.add(74381793);

        // before using erase() function
        System.out.println("Linked Blocking Deque: " + LBD);

        LBD.clear();
        // after using erase() function
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```java
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Linked Blocking Deque: []

```

**程序二:**

```java
// Java Program Demonstrate clear()
// method of LinkedBlockingDeque
// when the list contains characters
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
        LBD.add("1");
        LBD.add("2");
        LBD.add("3");
        LBD.add("4");

        // before using erase() function
        System.out.println("Linked Blocking Deque: " + LBD);

        LBD.clear();
        // after using erase() function
        System.out.println("Linked Blocking Deque: " + LBD);
    }
}
```

**输出:**

```java
Linked Blocking Deque: [1, 2, 3, 4]
Linked Blocking Deque: []

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedblockingrequest . html # clear()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#clear())