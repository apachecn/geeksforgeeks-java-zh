# Java 中的 copy onwriterarraylist addifabsend()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-addifabsend-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearraylist-addifabsent-method-in-java/)

**[copy onwriterarraylist](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)**的**addifabsend(E E)**方法在列表中没有元素的情况下，将参数中传递的元素追加到列表的末尾。向列表中添加新元素时，该函数返回 true。

**语法:**

```
public boolean addIfAbsent(E e)
```

**参数:**该函数接受单个强制参数**元素**，该元素指定了列表中不存在的元素。

**返回值:**如果添加到列表中，该函数返回*真*。

以下程序说明了上述功能:

**程序 1:**

```
// Java Program to illustrate the CopyOnWriteArrayList
// addIfAbsent(element) method in Java
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis
            = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis.addIfAbsent(2);
        ArrLis.addIfAbsent(3);
        ArrLis.addIfAbsent(4);
        ArrLis.addIfAbsent(7);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: " 
                                           + ArrLis);

        System.out.println("On adding 4 it returns " 
          + ArrLis.addIfAbsent(4) + " as it is present");
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [2, 3, 4, 7]
On adding 4 it returns false as it is present

```

**程序二:**

```
// Java Program to illustrate the CopyOnWriteArrayList
// addIfAbsent(element) method in Java
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<String> ArrLis
            = new CopyOnWriteArrayList<String>();

        // Add elements
        ArrLis.addIfAbsent("gopal");
        ArrLis.addIfAbsent("gfg");
        ArrLis.addIfAbsent("jgec");
        ArrLis.addIfAbsent("sudo");

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: " + ArrLis);

        System.out.println("On adding 'sudo' it returns " 
            + ArrLis.addIfAbsent("sudo") + " as it is present");
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [gopal, gfg, jgec, sudo]
On adding 'sudo' it returns false as it is present

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copyonwriterarylist . html # addifabsend-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#addIfAbsent-E-)