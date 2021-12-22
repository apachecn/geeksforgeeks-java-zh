# Java 中的 CopyOnWriteArrayList 克隆()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-clone-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearraylist-clone-method-in-java/)

**[copy onwriterarraylist](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)**的**克隆()**方法返回列表的浅拷贝。浅拷贝在同一索引中包含完全相同的元素。

**语法:**

```
public Object clone()
```

**参数:**函数不接受任何参数。

**返回值:**函数返回列表的克隆。

以下程序说明了上述功能:

**程序 1:**

```
// Java Program to illustrate the 
// CopyOnWriteArrayList clone() method in Java
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

        // clone of the arraylist
        System.out.println("CopyOnWriteArrayList: "
                                    + ArrLis.clone());
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [32, 67, 98, 100]
CopyOnWriteArrayList: [32, 67, 98, 100]

```

**程序二:**

```
// Java Program to illustrate the 
// CopyOnWriteArrayList clone() method in Java

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

        // clone of the arraylist
        System.out.println("CopyOnWriteArrayList: " 
                                  + ArrLis.clone());
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [gopal, gfg, jgec, sudo]
CopyOnWriteArrayList: [gopal, gfg, jgec, sudo]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copy onwriterarraylist . html # clone–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#clone--)