# Java 中的 CopyOnWriteArrayList size()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-size-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearraylist-size-method-in-java/)

**[的 **size()** 方法返回列表的大小。它返回列表中元素的数量。](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)**

**语法:**

```java
public int size()
```

**参数:**函数不接受任何参数。

**返回值:**函数返回列表的大小。

以下程序说明了上述功能:

**程序 1:**

```java
// Java Program to illustrate the CopyOnWriteArrayList
// size() method in Java
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
        ArrLis.add(98);
        ArrLis.add(100);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: "
                                          + ArrLis);

        // size value print
        System.out.println("size of ArrLis: " 
                              + ArrLis.size());
    }
}
```

**输出:**

```java
CopyOnWriteArrayList: [32, 67, 98, 100]
size of ArrLis: 4

```

**程序二:**

```java
// Java Program to illustrate the CopyOnWriteArrayList
// size() method in Java
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
        System.out.println("CopyOnWriteArrayList: " 
                                          + ArrLis);

        // size value print
        System.out.println("size of ArrLis: " 
                                + ArrLis.size());
    }
}
```

**输出:**

```java
CopyOnWriteArrayList: [gopal, gfg, jgec, sudo]
size of ArrLis: 4

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copy onwriterarraylist . html # size–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#size--)