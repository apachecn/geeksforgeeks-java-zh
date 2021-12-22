# Java 中的 CopyOnWriteArrayList isEmpty()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-isempty-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearraylist-isempty-method-in-java/)

**是 **[的空方法](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)** 检查列表是否为空。如果列表为空，则返回 true，否则返回 false。**

**语法:**

```
public boolean isEmpty()
```

**参数:**函数不接受任何参数。

**返回值:**如果列表为空，则函数返回*真*，否则返回假。

以下程序说明了上述功能:

**程序 1:**

```
// Java Program to illustrate the 
// isEmpty() method in Java
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
        if (ArrLis.isEmpty())
            System.out.println("List is empty");
        else
            System.out.println("List is not empty");

        ArrLis.clear();

        // check using function
        if (ArrLis.isEmpty())
            System.out.println("List is empty");
        else
            System.out.println("List is not empty");
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [32, 67, 98, 100]
List is not empty
List is empty

```

**程序二:**

```
// Java Program to illustrate the 
// isEmpty() method in Java
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
        if (ArrLis.isEmpty())
            System.out.println("List is empty");
        else
            System.out.println("List is not empty");

        ArrLis.clear();

        // check using function
        if (ArrLis.isEmpty())
            System.out.println("List is empty");
        else
            System.out.println("List is not empty");
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [gopal, gfg, jgec, sudo]
List is not empty
List is empty

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copyonwriterarylist . html # isEmpty–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#isEmpty--)