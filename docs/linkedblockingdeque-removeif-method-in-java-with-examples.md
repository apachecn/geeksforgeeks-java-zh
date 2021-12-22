# Java 中 link edblockingrequeremoveif()方法示例

> 原文:[https://www . geeksforgeeks . org/linkedblockingrequest-removeif-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedblockingdeque-removeif-method-in-java-with-examples/)

[链接锁定请求](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)的 **removeIf()** 方法从该链接锁定请求中移除满足指定条件的元素。

**语法:**

```
public boolean removeIf (Predicate<? super E> filter)
```

**参数:**该方法接受一个强制参数过滤器，该过滤器是谓词值，基于该值可以从该 Deque 中移除哪些元素。

**返回:**如果链接锁定请求被更改，该方法返回一个**布尔值**如真。否则此方法返回 false。

**异常:**如果指定的谓词过滤器为空，此方法将抛出**空指针异常**。

下面的程序说明了 LinkedBlockingDeque 类的 removeIf()函数:

**程序 1:**

```
// Java Program Demonstrate removeIf()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // Create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add(7855642);
        LBD.add(35658786);
        LBD.add(5278367);
        LBD.add(74381793);

        // Print Deque
        System.out.println("Linked Blocking Deque: "
                           + LBD);

        // If a number in the List is
        // divisible by 3, then remove it
        LBD.removeIf(number -> number % 3 == 0);

        System.out.println("Linked Blocking Deque: "
                           + LBD);
    }
}
```

**输出:**

```
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]
Linked Blocking Deque: [7855642, 5278367]

```

**程序二:**

```
// Java Program Demonstrate removeIf()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // Create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add(7855642);
        LBD.add(35658786);
        LBD.add(5278367);
        LBD.add(74381793);

        // Print Dequeue
        System.out.println("Linked Blocking Deque: "
                           + LBD);

        try {
            // if the predicate is null,
            // then it will throw NullPointerException
            LBD.removeIf(null);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]
java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/concurrent/linkedblockingrequest . html # removeIf-Java . util . function . predicate-](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/LinkedBlockingDeque.html#removeIf-java.util.function.Predicate-)