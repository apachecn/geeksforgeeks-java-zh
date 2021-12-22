# Java 中的 copy onwriterarraylist spliterator()方法

> 原文:[https://www . geesforgeks . org/copy onwriterarraylist-spliterator-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearraylist-spliterator-method-in-java/)

**[copy onwriterarraylist](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)**的 **spliterator()** 方法以适当的顺序返回该列表中元素的 spliterator。在拆分器上操作时不需要同步。

**语法:**

```
public Spliterator spliterator()
```

**参数:**函数不接受任何参数。

**返回值:**函数返回列表中元素的分隔符。

以下程序说明了上述功能:

**程序 1:**

```
// Java Program to illustrate the CopyOnWriteArrayList
// spliterator() method in Java
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis
            = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis.add(32);
        ArrLis.add(67);
        ArrLis.add(67);
        ArrLis.add(100);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: " + ArrLis);

        Spliterator<Integer> numbers = ArrLis.spliterator();

        // print result from Spliterator
        System.out.println("list of Numbers:");

        // forEachRemaining method  of Spliterator
        numbers.forEachRemaining((n) -> System.out.println(n));
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [32, 67, 67, 100]
list of Numbers:
32
67
67
100

```

**程序二:**

```
// Java Program to illustrate the CopyOnWriteArrayList
// spliterator() method in Java
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<String> ArrLis
            = new CopyOnWriteArrayList<String>();

        // Add elements
        ArrLis.add("gopal");
        ArrLis.add("gfg");
        ArrLis.add("jgec");
        ArrLis.add("sudo");

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: " + ArrLis);

        Spliterator<String> numbers = ArrLis.spliterator();

        // print result from Spliterator
        System.out.println("list of strings:");

        // forEachRemaining method  of Spliterator
        numbers.forEachRemaining((n) -> System.out.println(n));
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [gopal, gfg, jgec, sudo]
list of strings:
gopal
gfg
jgec
sudo

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copy onwriterarraylist . html # spliterator–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#spliterator--)