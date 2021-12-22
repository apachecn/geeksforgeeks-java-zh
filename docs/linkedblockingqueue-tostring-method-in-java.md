# Java 中 LinkedBlockingQueue toString()方法

> 原文:[https://www . geeksforgeeks . org/linkedblockingqueue-tostring-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingqueue-tostring-method-in-java/)

**的 **toString()** 方法链接锁定队列**返回该集合的字符串表示形式。字符串表示由集合元素的列表组成，这些元素按照迭代器返回的顺序排列，用方括号括起来**(“[]”**)。相邻的元素由字符**、“**(逗号和空格)分隔。元素被转换为字符串，如字符串值(对象)。

**语法:**

```java
public String toString()
```

**参数:**此方法不接受任何参数。

**返回:**该方法返回该集合的字符串表示形式。

以下程序说明了链接锁定队列的*到字符串()*方法:

**程序 1:**

```java
// Java Program Demonstrate toString()
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)

    {

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Integer> LBQ
            = new LinkedBlockingQueue<Integer>();

        // Add numbers to end of LinkedBlockingQueue
        LBQ.add(7855642);
        LBQ.add(35658786);
        LBQ.add(5278367);
        LBQ.add(74381793);

        // Print the queue
        System.out.println("Linked Blocking Queue: " + LBQ);

        System.out.println("Linked Blocking Queue in string " 
                                           + LBQ.toString());
    }
}
```

**输出:**

```java
Linked Blocking Queue: [7855642, 35658786, 5278367, 74381793]
Linked Blocking Queue in string [7855642, 35658786, 5278367, 74381793]

```

**程序二:**

```java
// Java Program Demonstrate toString()
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)

    {

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<String> LBQ
            = new LinkedBlockingQueue<String>();

        // Add numbers to end of LinkedBlockingQueue
        LBQ.add("gopal");
        LBQ.add("gate");
        LBQ.add("GRE");
        LBQ.add("CAT");

        // Print the queue
        System.out.println("Linked Blocking Queue: " + LBQ);

        System.out.println("Linked Blocking Queue in string " 
                                            + LBQ.toString());
    }
}
```

**输出:**

```java
Linked Blocking Queue: [gopal, gate, GRE, CAT]
Linked Blocking Queue in string [gopal, gate, GRE, CAT]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue . html # toString–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html#toString--)