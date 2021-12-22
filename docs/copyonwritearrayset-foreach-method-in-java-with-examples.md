# Java 中的 CopyOnWriteArraySet forEach()方法，带示例

> 原文:[https://www . geeksforgeeks . org/copy onwriterarrayset-foreach-method-in-Java-with-examples/](https://www.geeksforgeeks.org/copyonwritearrayset-foreach-method-in-java-with-examples/)

[copy onwriterarrayset](https://www.geeksforgeeks.org/copyonwritearrayset-in-java/)的 **forEach()** 方法是 Java 中的一个内置函数，用来遍历这个集合中的每个元素。

**语法:**

```
public void forEach (Consumer<E> action)

```

**参数:**该方法采用一个参数动作，代表每个元素要执行的动作。

**返回值:**这个方法不返回任何东西。

**异常:**如果指定的动作为空，该方法抛出**空指针异常**。

下面的程序说明了 CopyOnWriteArraySet 类的 forEach()函数:

**例 1:**

```
// Java Program to illustrate the CopyOnWriteArraySet
// forEach() method in Java

import java.util.concurrent.CopyOnWriteArraySet;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<Integer> ArrSet
            = new CopyOnWriteArraySet<Integer>();

        // Add elements
        ArrSet.add(2);
        ArrSet.add(3);
        ArrSet.add(4);
        ArrSet.add(7);
        ArrSet.add(8);

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);
        System.out.println("Traversing this Set: ");

        // Traverse this set using forEach() method
        ArrSet.forEach((n) -> System.out.println(n));
    }
}
```

**输出:**

```
CopyOnWriteArraySet: [2, 3, 4, 7, 8]
Traversing this Set: 
2
3
4
7
8

```

**例 2:**

```
// Java Program to illustrate the CopyOnWriteArraySet
// forEach() method in Java

import java.util.concurrent.CopyOnWriteArraySet;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<String> ArrSet
            = new CopyOnWriteArraySet<String>();

        // Add elements
        ArrSet.add("GeeksforGeeks");
        ArrSet.add("Geeks");
        ArrSet.add("Computer Science");
        ArrSet.add("Portal");
        ArrSet.add("Gfg");

        // Print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);
        System.out.println("Traversing this Set: ");

        // Traverse this set using forEach() method
        ArrSet.forEach((n) -> System.out.println(n));
    }
}
```

**输出:**

```
CopyOnWriteArraySet: [GeeksforGeeks, Geeks, Computer Science, Portal, Gfg]
Traversing this Set: 
GeeksforGeeks
Geeks
Computer Science
Portal
Gfg

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/concurrent/copy onwriterarrayset . html # forEach-Java . util . function . consumer-](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/CopyOnWriteArraySet.html#forEach-java.util.function.Consumer-)