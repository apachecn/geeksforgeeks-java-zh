# Java 中的 CopyOnWriteArrayList removeIf()方法，带示例

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-removeif-method-in-Java-with-examples/](https://www.geeksforgeeks.org/copyonwritearraylist-removeif-method-in-java-with-examples/)

[copy onwriterarraylist](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)的 **removeIf()** 方法从该 copy onwriterarraylist 中移除满足指定条件的元素。

**语法:**

```
public boolean removeIf (Predicate<E> filter)

```

**参数:**该方法接受强制参数过滤器，该过滤器是[谓词](https://www.geeksforgeeks.org/java-8-predicate-with-examples/)值，基于该值从该列表中移除元素。

**返回值:**如果[copy onwriterarraylist](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)发生变化，该方法返回一个**布尔值**如 true。否则此方法返回 false。

**异常:**如果指定的谓词过滤器为空，此方法将抛出 **[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)** 。

下面的程序说明了 CopyOnWriteArrayList 类的 removeIf()函数:

```
// Java Program to illustrate the CopyOnWriteArrayList
// removeIf() method in Java

import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis
            = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis.add(2);
        ArrLis.add(3);
        ArrLis.add(4);
        ArrLis.add(7);
        ArrLis.add(6);
        ArrLis.add(9);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: "
                           + ArrLis);

        // if a number in the List is
        // divisible by 3, then remove it
        ArrLis.removeIf(number -> number % 3 == 0);

        // print updated CopyOnWriteArrayList
        System.out.println("Updated CopyOnWriteArrayList: "
                           + ArrLis);
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [2, 3, 4, 7, 6, 9]
Updated CopyOnWriteArrayList: [2, 4, 7]

```

```
// Java Program to illustrate the CopyOnWriteArrayList
// removeIf() method in Java

import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<String> ArrLis
            = new CopyOnWriteArrayList<String>();

        // Add elements
        ArrLis.add("GeeksforGeeks");
        ArrLis.add("GFG");
        ArrLis.add("Geeks");
        ArrLis.add("Gfg");

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: "
                           + ArrLis);

        try {

            // This will throw NullPointerException
            ArrLis.removeIf(null);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [GeeksforGeeks, GFG, Geeks, Gfg]
java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/concurrent/copy onwriterarraylist . html # removeIf-Java . util . function . predicate-](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#removeIf-java.util.function.Predicate-)