# Java 中的 CopyOnWriteArraySet addAll()方法，带示例

> 原文:[https://www . geeksforgeeks . org/copy onwriterarrayset-addall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/copyonwritearrayset-addall-method-in-java-with-examples/)

[copy onwriterarrayset](https://www.geeksforgeeks.org/copyonwritearrayset-in-java/)方法的 **addAll()** 方法将指定集合中不存在的所有元素添加到该 copy onwriterarrayset 中。这些方法导致两个集合的联合。

**语法:**

```
public boolean addAll(Collection<E> c)
```

**参数:**该方法接受一个参数 **c** ，该参数是包含要添加到该集合中的元素的集合。

**返回值:**这个方法返回一个**布尔值**，比如 true，如果 CopyOnWriteArraySet 被改变的话。否则此方法返回 false。

**异常:**如果指定的集合为空，该方法抛出**空指针异常**。

下面的程序说明了 CopyOnWriteArrayList 类的 addAll()函数:

**程序 1:** 在下面的程序中，指定的集合元素被添加到 CopyOnWriteArraySet 中。由于 50 在两个集合中都很常见，所以只添加一次。

```
// Java Program to illustrate the
// CopyOnWriteArraySet addall() method in Java

import java.util.concurrent.CopyOnWriteArraySet;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<Integer> ArrSet
            = new CopyOnWriteArraySet<Integer>();

        // Add elements
        ArrSet.add(10);
        ArrSet.add(20);
        ArrSet.add(30);
        ArrSet.add(50);

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

        // create object of ArrayList
        ArrayList<Integer> Arrlist
            = new ArrayList<Integer>();

        // Add elements
        Arrlist.add(50);
        Arrlist.add(60);
        Arrlist.add(70);
        Arrlist.add(80);

        // print ArrayList
        System.out.println("ArrayList:  "
                           + Arrlist);

        // adding all elements of Arraylist
        // in the CopyOnWriteArraySet
        ArrSet.addAll(Arrlist);

        // print updated CopyOnWriteArraySet
        System.out.println("Updated CopyOnWriteArraySet: "
                           + ArrSet);
    }
}
```

**Output:**

```
CopyOnWriteArraySet: [10, 20, 30, 50]
ArrayList:  [50, 60, 70, 80]
Updated CopyOnWriteArraySet: [10, 20, 30, 50, 60, 70, 80]

```

**程序 2:** 显示空指针异常

```
// Java Program to illustrate the
// CopyOnWriteArraySet addall() method in Java

import java.util.concurrent.CopyOnWriteArraySet;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<Integer> ArrSet
            = new CopyOnWriteArraySet<Integer>();

        // Add elements
        ArrSet.add(10);
        ArrSet.add(20);
        ArrSet.add(30);
        ArrSet.add(50);

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

        // create object of ArrayList
        ArrayList<Integer> Arrlist
            = new ArrayList<Integer>();

        try {

            // adding null to the CopyOnWriteArraySet
            // This will throw NullPointerException
            ArrSet.addAll(null);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
CopyOnWriteArraySet: [10, 20, 30, 50]
java.lang.NullPointerException

```