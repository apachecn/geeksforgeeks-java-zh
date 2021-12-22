# Java 中的 CopyOnWriteArraySet clear()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarrayset-clear-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearrayset-clear-method-in-java/)

**[的 **clear()** 方法](https://www.geeksforgeeks.org/copyonwritearrayset-in-java/)** 会擦除集合中的所有元素。调用函数后，集合的大小变为零。

**语法:**

```
public void clear()
```

**返回值:**函数不返回任何内容。

以下程序说明了上述功能:

**程序 1:**

```
// Java Program to illustrate the CopyOnWriteArraySet
// clear() method in Java

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
        ArrSet.add(98);

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

        // Clear the CopyOnWriteArraySet
        // Using clear() method
        ArrSet.clear();

        System.out.println("\nCopyOnWriteArraySet cleared\n");

        // Print the updated CopyOnWriteArraySet
        System.out.println("Updated CopyOnWriteArraySet: "
                           + ArrSet);
    }
}
```

**输出:**

```
CopyOnWriteArraySet: [32, 67, 98]

CopyOnWriteArraySet cleared

Updated CopyOnWriteArraySet: []

```

**程序二:**

```
// Java Program to illustrate the CopyOnWriteArraySet
// clear() method in Java

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
        ArrSet.add("gfg");
        ArrSet.add("jgec");
        ArrSet.add("jgec");

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

        // Clear the CopyOnWriteArraySet
        // Using clear() method
        ArrSet.clear();

        System.out.println("\nCopyOnWriteArraySet cleared\n");

        // Print the updated CopyOnWriteArraySet
        System.out.println("Updated CopyOnWriteArraySet: "
                           + ArrSet);
    }
}
```

**输出:**

```
CopyOnWriteArraySet: [gopal, gfg, jgec]

CopyOnWriteArraySet cleared

Updated CopyOnWriteArraySet: []

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copy onwriterarrayset . html # clear–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArraySet.html#clear--)