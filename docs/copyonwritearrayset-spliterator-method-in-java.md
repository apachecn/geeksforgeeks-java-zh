# Java 中的 copy onwriterarrayset spliterator()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarrayset-spliterator-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearrayset-spliterator-method-in-java/)

**[copy onwriterarrayset](https://www.geeksforgeeks.org/copyonwritearrayset-in-java/)**的**拆分器()**方法按正确的顺序返回该集合中元素的拆分器。在拆分器上操作时不需要同步。

**语法:**

```java
public Spliterator spliterator()
```

**返回值:**该函数在集合中的元素上返回**一个分割器**。

以下程序说明了上述功能:

**程序 1:**

```java
// Java Program to illustrate the CopyOnWriteArraySet
// spliterator() method in Java

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

        Spliterator<Integer>
            numbers = ArrSet.spliterator();

        // print result from Spliterator
        System.out.println("Set of Numbers:");

        // forEachRemaining method  of Spliterator
        numbers
            .forEachRemaining(
                (n) -> System.out.println(n));
    }
}
```

**输出:**

```java
CopyOnWriteArraySet: [32, 67, 100]
Set of Numbers:
32
67
100

```

**程序二:**

```java
// Java Program to illustrate the CopyOnWriteArraySet
// spliterator() method in Java

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

        Spliterator<String>
            numbers = ArrSet.spliterator();

        // print result from Spliterator
        System.out.println("Set of strings:");

        // forEachRemaining method  of Spliterator
        numbers
            .forEachRemaining(
                (n) -> System.out.println(n));
    }
}
```

**输出:**

```java
CopyOnWriteArraySet: [gopal, gfg, jgec, sudo]
Set of strings:
gopal
gfg
jgec
sudo

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copy onwriterarrayset . html # spliterator–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArraySet.html#spliterator--)