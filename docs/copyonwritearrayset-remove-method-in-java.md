# Java 中的 CopyOnWriteArraySet remove()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarrayset-remove-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearrayset-remove-method-in-java/)

**[copy onwriterarrayset](https://www.geeksforgeeks.org/copyonwritearrayset-in-java/)**的 **remove()** 方法移除集合中存在的指定元素。

**语法:**

```java
public boolean remove(Object o)
```

**参数:**该功能接受一个强制参数 **o** ，该参数指定要从集合中移除的元素(如果存在)。

**返回值:**如果集合包含指定元素，则函数返回*真*。

以下程序说明了上述功能:

**程序 1:**

```java
// Java Program to illustrate the
// remove() method in Java

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
        ArrSet.add(98);
        ArrSet.add(100);

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

        // Remove using remove() function
        if (ArrSet.remove(100))
            System.out.println("Set after removal"
                               + " of 100 is: "
                               + ArrSet);
        else
            System.out.println("100 is not present");
    }
}
```

**输出:**

```java
CopyOnWriteArraySet: [32, 67, 98, 100]
Set after removal of 100 is: [32, 67, 98]

```

**程序二:**

```java
// Java Program to illustrate the
// isEmpty() method in Java

import java.util.concurrent.CopyOnWriteArraySet;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<String> ArrSet
            = new CopyOnWriteArraySet<String>();

        // Add elements
        ArrSet.add("gopal");
        ArrSet.add("geeks");
        ArrSet.add("geeks");
        ArrSet.add("technical");

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

        // Remove using remove() function
        if (ArrSet.remove("scripter"))
            System.out.println("Set after removal"
                               + " of 'scripter' is: "
                               + ArrSet);
        else
            System.out.println("'scripter' is not present");
    }
}
```

**输出:**

```java
CopyOnWriteArraySet: [gopal, geeks, technical]
'scripter' is not present

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copy onwriterarrayset . html # remove-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArraySet.html#remove-java.lang.Object-)