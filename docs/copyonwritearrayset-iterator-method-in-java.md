# Java 中的 CopyOnWriteArraySet 迭代器()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarrayset-iterator-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearrayset-iterator-method-in-java/)

**[的**迭代器()方法**](https://www.geeksforgeeks.org/copyonwritearrayset-in-java/)** 以适当的顺序返回该集合中元素的迭代器。迭代器不支持移除方法。

**语法:**

```java
public Iterator iterator()
```

**返回值:**函数在集合中的元素上返回**迭代器**。

以下程序说明了上述功能:

**程序 1:**

```java
// Java Program to illustrate the CopyOnWriteArraySet
// iterator() method in Java

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

        // Call iterator() method of
        Iterator iteratorVals = ArrSet.iterator();

        // Print elements of iterator
        // created from CopyOnWriteArraySet
        System.out.println("\nThe iterator values of "
                           + "CopyOnWriteArraySet are:\n");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

**输出:**

```java
CopyOnWriteArraySet: [32, 67, 100]

The iterator values of CopyOnWriteArraySet are:

32
67
100

```

**程序二:**

```java
// Java Program to illustrate the CopyOnWriteArraySet
// iterator() method in Java

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
        ArrSet.add("sudo");

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

        // Call iterator() method of
        Iterator iteratorVals = ArrSet.iterator();

        // Print elements of iterator
        // created from CopyOnWriteArraySet
        System.out.println("\nThe iterator values of "
                           + "CopyOnWriteArraySet are:\n");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

**输出:**

```java
CopyOnWriteArraySet: [gopal, gfg, jgec, sudo]

The iterator values of CopyOnWriteArraySet are:

gopal
gfg
jgec
sudo

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copy onwriterarrayset . html #迭代器–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArraySet.html#iterator--)