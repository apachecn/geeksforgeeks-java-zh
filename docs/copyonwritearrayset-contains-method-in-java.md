# copy onwriterarrayset 在 Java 中包含()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarrayset-contains-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearrayset-contains-method-in-java/)

**包含**的**方法检查给定元素是否存在于集合中。**

**语法:**

```java
public boolean contains(Object o)
```

**参数:**该功能接受单个强制参数 **o** ，该参数指定要在集合中检查外观的元素。

**返回值:**函数返回*真*如果元素存在，则返回假。

以下程序说明了上述功能:

**程序 1:**

```java
// Java Program to illustrate the CopyOnWriteArraySet
// contains() method in Java

import java.util.concurrent.CopyOnWriteArraySet;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<Integer> ArrSet
            = new CopyOnWriteArraySet<Integer>();

        // Add elements
        ArrSet.add(32);
        ArrSet.add(67);
        ArrSet.add(67);
        ArrSet.add(100);

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

        // check if 100 is present
        // using contains() function
        if (ArrSet.contains(100))
            System.out.println("100 is "
                               + "present in the Set");
        else
            System.out.println("100 is "
                               + "not present in the Set");

        // check if 20 is present
        // using contains() function
        if (ArrSet.contains(20))
            System.out.println("20 is "
                               + "present in the Set");
        else
            System.out.println("20 is "
                               + "not present in the Set");
    }
}
```

**输出:**

```java
CopyOnWriteArraySet: [32, 67, 100]
100 is present in the Set
20 is not present in the Set

```

**程序二:**

```java
// Java Program to illustrate the CopyOnWriteArraySet
// contains() method in Java

import java.util.concurrent.CopyOnWriteArraySet;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<String> ArrSet
            = new CopyOnWriteArraySet<String>();

        // Add elements
        ArrSet.add("geeks");
        ArrSet.add("gfg");
        ArrSet.add("jgec");
        ArrSet.add("sudo");

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

        // check using contains() function
        if (ArrSet.contains("gfg"))
            System.out.println("gfg is "
                               + "present in the Set");
        else
            System.out.println("gfg is "
                               + "not present in the Set");

        // check using contains() function
        if (ArrSet.contains("best"))
            System.out.println("best is "
                               + "present in the Set");
        else
            System.out.println("best is "
                               + "not present in the Set");
    }
}
```

**输出:**

```java
CopyOnWriteArraySet: [geeks, gfg, jgec, sudo]
gfg is present in the Set
best is not present in the Set

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copy onwriterarrayset . html # contains-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArraySet.html#contains-java.lang.Object-)