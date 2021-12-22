# Java 中 link edblockingrequeremoveall()方法示例

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-remove all-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedblockingdeque-removeall-method-in-java-with-examples/)

[的 **removeAll()** 方法 link edblockingrequest](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)是一个内置函数，是 Java，用于从这个对象中移除指定集合中包含的所有元素。这意味着，这两个集合的所有公共元素都将从这个 deque 中移除。
**语法:**

```java
public boolean removeAll(Collection c)
```

**参数:**该方法将集合 **c** 作为包含要从该列表中移除的元素的参数。
**返回值:**如果调用导致该德奎发生变化，则该方法返回真。
**异常:**如果指定的集合为空，该方法抛出**空指针异常**。
下面的程序说明了 LinkedBlockingDeque 类的 removeAll()函数:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate removeAll()
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
        LBD.add(11);
        LBD.add(22);
        LBD.add(33);
        LBD.add(44);

        // print deque
        System.out.println("Linked Blocking Deque: "
                           + LBD);

        // create object of ArrayList collection
        ArrayList<Integer> ArrLis
            = new ArrayList<Integer>();

        // Add number to ArrayList
        ArrLis.add(55);
        ArrLis.add(11);
        ArrLis.add(23);
        ArrLis.add(22);

        // print ArrayList
        System.out.println("ArrayList to be removed: "
                           + ArrLis);

        // function removeAll() removes all
        // the common elements from deque
        LBD.removeAll(ArrLis);

        // print deque
        System.out.println("Current Linked Blocking Deque: "
                           + LBD);
    }
}
```

**Output**

```java
Linked Blocking Deque: [11, 22, 33, 44]
ArrayList to be removed: [55, 11, 23, 22]
Current Linked Blocking Deque: [33, 44]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate removeAll()
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
        LBD.add("geeks");
        LBD.add("Geeks");
        LBD.add("gfg");
        LBD.add("Gfg");

        // print deque
        System.out.println("Linked Blocking Deque: "
                           + LBD);

        // create object of ArrayList collection
        ArrayList<String> ArrLis
            = new ArrayList<String>();

        // Add number to ArrayList
        ArrLis.add("GeeksforGeeks");
        ArrLis.add("Geeks");
        ArrLis.add("gfg");
        ArrLis.add("Gfg");

        // print ArrayList
        System.out.println("ArrayList: "
                           + ArrLis);

        // function removeAll() removes all
        // the common elements from deque
        LBD.removeAll(ArrLis);

        // print deque
        System.out.println("Linked Blocking Deque: "
                           + LBD);
    }
}
```

**Output**

```java
Linked Blocking Deque: [geeks, Geeks, gfg, Gfg]
ArrayList: [GeeksforGeeks, Geeks, gfg, Gfg]
Linked Blocking Deque: [geeks]
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/concurrent/linkedblockingrequest . html # removeAll-Java . util . collection-](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/LinkedBlockingDeque.html#removeAll-java.util.Collection-)