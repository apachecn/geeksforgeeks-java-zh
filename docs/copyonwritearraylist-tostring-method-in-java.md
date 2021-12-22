# Java 中的 CopyOnWriteArrayList toString()方法

> 原文:[https://www . geesforgeks . org/copy onwriterarraylist-tostring-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearraylist-tostring-method-in-java/)

**[的 **toString()** 方法返回列表的字符串表示形式。](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)**

**语法:**

```
public String toString()
```

**参数:**函数不接受任何参数。

**返回值:**函数返回列表的字符串表示形式。

以下程序说明了上述功能:

**程序 1:**

```
// Java Program to illustrate the CopyOnWriteArrayList
// toString() method in Java
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

        System.out.println("ArrLis converted to string: " 
                                    + ArrLis.toString());
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [32, 67, 98, 100]
ArrLis converted to string: [32, 67, 98, 100]

```

**程序二:**

```
// Java Program to illustrate the CopyOnWriteArrayList
// toString()() method in Java
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

        System.out.println("ArrLis converted to string: " 
                                      + ArrLis.toString());
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [gopal, gfg, jgec, sudo]
ArrLis converted to string: [gopal, gfg, jgec, sudo]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copyonwriterarylist . html # toString–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#toString--)