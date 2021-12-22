# Java 中的 CopyOnWriteArrayList forEach()方法，带示例

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-foreach-method-in-Java-with-examples/](https://www.geeksforgeeks.org/copyonwritearraylist-foreach-method-in-java-with-examples/)

[copy onwriterarraylist](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)的 **forEach()** 方法为 Iterable 的每个元素执行给定的操作，直到所有元素都被处理完或者该操作引发异常。

**语法:**

```java
public void forEach (Consumer<E> action)
```

**参数:**该方法取一个参数**动作**，代表每个元素要执行的动作。

**返回:**这个方法不返回任何东西。

**异常:**如果指定的动作为空，该方法抛出**空指针异常**。

下面的程序说明了 CopyOnWriteArrayList 类的 forEach()函数:

**程序 1:**

```java
// Java Program to illustrate the CopyOnWriteArrayList
// forEach() method in Java

import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis
            = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis.add(2);
        ArrLis.add(3);
        ArrLis.add(4);
        ArrLis.add(7);

        // Print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: "
                           + ArrLis);

        System.out.println("Traversing this List : ");

        // Traverse this queue using forEach() method
        ArrLis.forEach((n) -> System.out.println(n));
    }
}
```

**输出:**

```java
CopyOnWriteArrayList: [2, 3, 4, 7]
Traversing this List : 
2
3
4
7

```

**程序二:**

```java
// Java Program to illustrate the CopyOnWriteArrayList
// forEach() method in Java

import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<String> ArrLis
            = new CopyOnWriteArrayList<String>();

        // Add elements
        ArrLis.add("Geeks");
        ArrLis.add("Gfg");
        ArrLis.add("Portal");
        ArrLis.add("geeksforgeeks");

        // Print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: "
                           + ArrLis);

        System.out.println("Traversing this List : ");

        // Traverse this queue using forEach() method
        ArrLis.forEach((n) -> System.out.println(n));
    }
}
```

**输出:**

```java
CopyOnWriteArrayList: [Geeks, Gfg, Portal, geeksforgeeks]
Traversing this List : 
Geeks
Gfg
Portal
geeksforgeeks

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copy onwriterarraylist . html # forEach-Java . util . function . consumer-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#forEach-java.util.function.Consumer-)