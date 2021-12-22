# Java 中的 CopyOnWriteArrayList hashCode()方法

> 原文:[https://www . geesforgeks . org/copy onwriterarraylist-hashcode-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearraylist-hashcode-method-in-java/)

**[的 **hashCode()** 方法返回列表的 hashCode 值。](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)**

**语法:**

```
public int hashCode()
```

**参数:**函数不接受任何参数。

**返回值:**函数返回列表的 hashCode 值。

以下程序说明了上述功能:

**程序 1:**

```
// Java Program to illustrate the CopyOnWriteArrayList
// hashCode() method in Java
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

        // hashCode value print
        System.out.println("hashCode value: " 
                          + ArrLis.hashCode());
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [32, 67, 98, 100]
hashCode value: 1944358

```

**程序二:**

```
// Java Program to illustrate the CopyOnWriteArrayList
// hashCode() method in Java
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

        // hashCode value print
        System.out.println("hashCode value: " 
                          + ArrLis.hashCode());
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [gopal, gfg, jgec, sudo]
hashCode value: -1942417272

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copy onwriterarraylist . html # hashCode–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#hashCode--)