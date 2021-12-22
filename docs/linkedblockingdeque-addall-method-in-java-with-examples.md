# 用示例链接 Java 中的 linkedblockingrequeaddall()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-addall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedblockingdeque-addall-method-in-java-with-examples/)

[的 **addAll()** 方法将指定集合的所有元素追加到这个 Deque 的末尾。
**语法:**](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/) 

```
public void addAll(Collection<E> c)
```

**参数:**这个方法接受一个强制参数 **c** ，它是要插入到 link edblockingrequest 末尾的集合。
**返回值:**这个方法不返回任何东西。
**异常:**存在 2 个异常:-

*   **illegalstatexception**:如果此时由于容量限制无法添加集合。
*   **NullPointRexception**:如果指定的集合为空。

下面的程序说明了 LinkedBlockingDeque 类的 addAll()函数:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate addAll()
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

        // Print deque
        System.out.println("Linked Blocking Deque: "
                           + LBD);

        // Create object of ArrayList collection
        ArrayList<Integer> ArrLis
            = new ArrayList<Integer>();

        // Add number to ArrayList
        ArrLis.add(55);
        ArrLis.add(66);
        ArrLis.add(77);
        ArrLis.add(88);

        // Print ArrayList
        System.out.println("ArrayList: "
                           + ArrLis);

        // Function addAll() adds all the elements of
        // ArrayList to Deque
        LBD.addAll(ArrLis);

        // Print deque
        System.out.println("Linked Blocking Deque: "
                           + LBD);
    }
}
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate addAll()
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

        // Add elements to end of LinkedBlockingDeque
        LBD.add("GeeksforGeeks");
        LBD.add("Gfg");
        LBD.add("Geeks");

        // Print deque
        System.out.println("Linked Blocking Deque: "
                           + LBD);

        // Create object of ArrayList collection
        ArrayList<String> ArrLis
            = new ArrayList<String>();

        // Add elements to ArrayList
        ArrLis.add("Computer");
        ArrLis.add("Science");
        ArrLis.add("Portal");

        // Print ArrayList
        System.out.println("ArrayList: " + ArrLis);

        // Function addAll() adds all the elements of
        // ArrayList to Deque
        LBD.addAll(ArrLis);

        // Print deque
        System.out.println("Linked Blocking Deque: "
                           + LBD);
    }
}
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/concurrent/linkedblockingrequest . html # addAll-Java . util . collection-](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/LinkedBlockingDeque.html#addAll-java.util.Collection-)