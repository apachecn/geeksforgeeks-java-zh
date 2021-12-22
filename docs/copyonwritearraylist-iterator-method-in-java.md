# Java 中的 CopyOnWriteArrayList 迭代器()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-iterator-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearraylist-iterator-method-in-java/)

的**迭代器()**方法以适当的顺序返回该列表中元素的迭代器。迭代器不支持移除方法。

**语法:**

```java
public Iterator iterator()
```

**参数:**函数不接受任何参数。

**返回值:**函数返回列表中元素的迭代器。

以下程序说明了上述功能:

**程序 1:**

```java
// Java Program to illustrate the CopyOnWriteArrayList
// iterator() method in Java
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
        ArrLis.add(67);
        ArrLis.add(100);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: " + ArrLis);

        // Call iterator() method of
        Iterator iteratorVals = ArrLis.iterator();

        // Print elements of iterator
        // created from CopyOnWriteArrayList
        System.out.println("The iterator values"
                           + " of CopyOnWriteArrayList are:");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

**输出:**

```java
CopyOnWriteArrayList: [32, 67, 67, 100]
The iterator values of CopyOnWriteArrayList are:
32
67
67
100

```

**程序二:**

```java
// Java Program to illustrate the CopyOnWriteArrayList
// iterator() method in Java
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

        // Call iterator() method of
        Iterator iteratorVals = ArrLis.iterator();

        // Print elements of iterator
        // created from CopyOnWriteArrayList
        System.out.println("The iterator values"
                           + " of CopyOnWriteArrayList are:");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

**输出:**

```java
CopyOnWriteArrayList: [gopal, gfg, jgec, sudo]
The iterator values of CopyOnWriteArrayList are:
gopal
gfg
jgec
sudo

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copy onwriterarraylist . html #迭代器–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#iterator--)