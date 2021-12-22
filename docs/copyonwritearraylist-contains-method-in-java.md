# copy onwriterarraylist 在 Java 中包含()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-contains-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearraylist-contains-method-in-java/)

**包含 **[的(E e)](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)** 方法检查列表中是否存在给定的元素。如果元素至少出现一次，则函数返回 true，否则返回 false。**

**语法:**

```java
public boolean contains(Object o)
```

**参数:**该函数接受单个强制参数 **o** ，该参数指定要在列表中检查其外观的元素。

**返回值:**如果元素在列表中至少出现一次，函数返回*真*，否则返回假。

以下程序说明了上述功能:

**程序 1:**

```java
// Java Program to illustrate the CopyOnWriteArrayList
// contains() method in Java
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
        System.out.println("CopyOnWriteArrayList: " + ArrLis);

        // check using function
        if (ArrLis.contains(100))
            System.out.println("100 is present in the list");
        else
            System.out.println("100 is not present in the list");

        // check using function
        if (ArrLis.contains(20))
            System.out.println("20 is present in the list");
        else
            System.out.println("20 is not present in the list");
    }
}
```

**输出:**

```java
CopyOnWriteArrayList: [32, 67, 98, 100]
100 is present in the list
20 is not present in the list

```

**程序二:**

```java
// Java Program to illustrate the CopyOnWriteArrayList
// contains() method in Java
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

        // check using function
        if (ArrLis.contains("gfg"))
            System.out.println("'gfg' is present in the list");
        else
            System.out.println("'gfg' is not present in the list");

        // check using function
        if (ArrLis.contains("best"))
            System.out.println("'best' is present in the list");
        else
            System.out.println("'best' is not present in the list");
    }
}
```

**输出:**

```java
CopyOnWriteArrayList: [gopal, gfg, jgec, sudo]
'gfg' is present in the list
'best' is not present in the list

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copy onwriterarraylist . html # contains-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#contains-E-)