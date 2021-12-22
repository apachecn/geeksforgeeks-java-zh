# Java 中的 CopyOnWriteArraySet removeIf()方法，带示例

> 原文:[https://www . geeksforgeeks . org/copy onwriterarrayset-removeif-method-in-Java-with-examples/](https://www.geeksforgeeks.org/copyonwritearrayset-removeif-method-in-java-with-examples/)

[copy onwriterarrayset](https://www.geeksforgeeks.org/copyonwritearrayset-in-java/)方法的 **removeIf()** 方法从该 copy onwriterarrayset 中移除满足指定条件的元素。

**语法:**

```java
public boolean removeIf (Predicate<E> filter)
```

**参数:**该方法接受一个强制参数**过滤器**，它是谓词值，基于该值从该集合中移除元素。

**返回值:**这个方法返回一个**布尔值**，比如 true，如果 CopyOnWriteArraySet 被改变的话。否则此方法返回 false。

**异常:**如果指定的谓词过滤器为空，此方法将抛出**空指针异常**。

下面的程序说明了 CopyOnWriteArrayList 类的 removeIf()函数:

**程序 1:**

```java
// Java Program to illustrate the CopyOnWriteArraySet
// removeIf() method in Java

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
        ArrSet.add(40);
        ArrSet.add(50);
        ArrSet.add(60);
        ArrSet.add(70);
        ArrSet.add(80);
        ArrSet.add(90);

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

        // if a number in the set is
        // divisible by 3, then remove it
        ArrSet.removeIf(number -> number % 3 == 0);

        // print updated CopyOnWriteArraySet
        System.out.println("Updated CopyOnWriteArraySet: "
                           + ArrSet);
    }
}
```

**Output:**

```java
CopyOnWriteArraySet: [10, 20, 30, 40, 50, 60, 70, 80, 90]
Updated CopyOnWriteArraySet: [10, 20, 40, 50, 70, 80]

```

**程序 2:**

```java
// Java Program to illustrate the CopyOnWriteArraySet
// removeIf() method in Java

import java.util.concurrent.CopyOnWriteArraySet;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<String> ArrSet
            = new CopyOnWriteArraySet<String>();

        // Add elements
        ArrSet.add("GeeksforGeeks");
        ArrSet.add("GFG");
        ArrSet.add("Geeks");
        ArrSet.add("Gfg");

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

        try {

            // if a number in the set is
            // divisible by 3, then remove it
            // This will throw NullPointerException
            ArrSet.removeIf(null);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
CopyOnWriteArraySet: [GeeksforGeeks, GFG, Geeks, Gfg]
java.lang.NullPointerException

```