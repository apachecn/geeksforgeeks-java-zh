# 用示例链接 Java 中的 linkedblockingrequeretainall()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-retain all-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedblockingdeque-retainall-method-in-java-with-examples/)

[link edblockingrequest](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)的**retainnal()**方法是一个内置函数，它是 Java，用于从这个对象中移除指定集合中包含的所有元素。这意味着，这两个集合的所有公共元素都将从这个 deque 中移除。

**语法:**

```
public boolean retainAll(Collection c)

```

**参数:**该方法将集合 **c** 作为包含要从该列表中移除的元素的参数。

**返回值:**如果调用的结果改变了这个值，这个方法返回真。

**异常:**如果指定的集合为空，该方法抛出**空指针异常**。

下面的程序说明了 LinkedBlockingDeque 类的 retainAll()函数:

**例 1:**

```
// Java Program Demonstrate retainAll()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // Create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add(11);
        LBD.add(22);
        LBD.add(33);
        LBD.add(44);

        // print deque
        System.out.println("Linked Blocking Deque: "
                           + LBD);

        // Create object of ArrayList collection
        ArrayList<Integer> ArrLis
            = new ArrayList<Integer>();

        // Add number to ArrayList
        ArrLis.add(55);
        ArrLis.add(11);
        ArrLis.add(23);
        ArrLis.add(22);

        // Print ArrayList
        System.out.println("ArrayList to be retained: "
                           + ArrLis);

        // Function retainAll() retains
        // all the common elements from deque
        LBD.retainAll(ArrLis);

        // Print deque
        System.out.println("Retained Linked Blocking Deque: "
                           + LBD);
    }
}
```

**输出:**

```
Linked Blocking Deque: [11, 22, 33, 44]
ArrayList to be retained: [55, 11, 23, 22]
Retained Linked Blocking Deque: [11, 22]

```

**例 2:**

```
// Java Program Demonstrate retainAll()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // Create object of LinkedBlockingDeque
        LinkedBlockingDeque<String> LBD
            = new LinkedBlockingDeque<String>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add("geeks");
        LBD.add("Geeks");
        LBD.add("gfg");
        LBD.add("Gfg");

        // Print deque
        System.out.println("Linked Blocking Deque: "
                           + LBD);

        // Create object of ArrayList collection
        ArrayList<String> ArrLis
            = new ArrayList<String>();

        // Add elements to ArrayList
        ArrLis.add("GeeksforGeeks");
        ArrLis.add("Geeks");
        ArrLis.add("gfg");
        ArrLis.add("Gfg");

        // Print ArrayList
        System.out.println("ArrayList to be retained: "
                           + ArrLis);

        // Function retainAll() retains
        // all the common elements from deque
        LBD.retainAll(ArrLis);

        // Print deque
        System.out.println("Retained Linked Blocking Deque: "
                           + LBD);
    }
}
```

**输出:**

```
Linked Blocking Deque: [geeks, Geeks, gfg, Gfg]
ArrayList to be retained: [GeeksforGeeks, Geeks, gfg, Gfg]
Retained Linked Blocking Deque: [Geeks, gfg, Gfg]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/concurrent/linkedblockingrequest . html # retailnall-Java . util . collection-](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/LinkedBlockingDeque.html#retainAll-java.util.Collection-)