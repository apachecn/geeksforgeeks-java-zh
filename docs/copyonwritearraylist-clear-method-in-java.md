# Java 中的 CopyOnWriteArrayList clear()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-clear-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearraylist-clear-method-in-java/)

的 **clear()** 方法会擦除列表中的所有元素。调用函数后，列表的大小变为零。

**语法:**

```java
public void clear()
```

**参数:**函数不接受任何参数。

**返回值:**函数不返回任何内容。

以下程序说明了上述功能:

**程序 1:**

```java
// Java Program to illustrate the CopyOnWriteArrayList
// clear() method in Java
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

        ArrLis.clear();

        System.out.println("CopyOnWriteArrayList: " 
                                         + ArrLis);
    }
}
```

**输出:**

```java
CopyOnWriteArrayList: [32, 67, 98, 100]
CopyOnWriteArrayList: []

```

**程序二:**

```java
// Java Program to illustrate the CopyOnWriteArrayList
// clear() method in Java
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

        ArrLis.clear();

        System.out.println("CopyOnWriteArrayList: " 
                                         + ArrLis);
    }
}
```

**输出:**

```java
CopyOnWriteArrayList: [gopal, gfg, jgec, sudo]
CopyOnWriteArrayList: []

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copy onwriterarraylist . html # clear–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#clear--)