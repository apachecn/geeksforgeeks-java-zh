# Java 中的 CopyOnWriteArrayList get()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-get-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearraylist-get-method-in-java/)

的 **get(index)** 方法返回指定索引处的元素。

**语法:**

```
public E get(int index)
```

**参数:**该函数接受一个强制参数索引，该索引指定要返回的元素的索引。

**返回值:**函数返回给定索引处的元素。

**异常:**如果指数超出范围，函数将抛出*指数。*

以下程序说明了上述功能:

**程序 1:**

```
// Java Program to illustrate the 
// CopyOnWriteArrayList get() method in Java
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

        // 2nd index in the arraylist
        System.out.println("Element at 2nd index: " 
                                    + ArrLis.get(2));
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [32, 67, 98, 100]
Element at 2nd index: 98

```

**节目 2:**

```
// Java Program to illustrate the 
// CopyOnWriteArrayList get() method in Java
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

        // 4th index element of the arraylist
        // out of range, hence error
        System.out.println("CopyOnWriteArrayList: "
                                    + ArrLis.get(4));
    }
}
```

**输出:**

```
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: 4
    at java.util.concurrent.CopyOnWriteArrayList.get(CopyOnWriteArrayList.java:388)
    at java.util.concurrent.CopyOnWriteArrayList.get(CopyOnWriteArrayList.java:397)
    at GFG.main(GFG.java:24)
```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copy onwriterarraylist . html # get-int-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#get-int-)