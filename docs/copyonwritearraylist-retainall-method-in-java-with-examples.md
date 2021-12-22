# Java 中的 CopyOnWriteArrayList retainAll()方法，带示例

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-retain all-method-in-Java-with-examples/](https://www.geeksforgeeks.org/copyonwritearraylist-retainall-method-in-java-with-examples/)

**T1 列表。Java 中的 retainAll()** 方法用于只保留列表中包含在特定集合中的元素。

**语法:**

```java
 public boolean retainAll(Collection col) 
```

**参数:**该方法接受集合类型的强制参数 **col** 。这是要保留在该向量中的元素的集合。

**返回类型:**如果由于调用 else 而导致列表发生变化，则该方法返回一个**布尔值** true。

**异常:**如果指定的集合为空，此方法将引发 NullPointerException。

下面的程序说明了 Java 中 CopyOnArrayList 的 retainAll()方法:

**程序 1:** 该程序涉及整数类型的 CopyOnArraylist retainAll()方法:

```java
// Java Program to illustrate CopyOnArrayList
// retainAll() method
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis1
            = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis1.add(34);
        ArrLis1.add(66);
        ArrLis1.add(72);
        ArrLis1.add(10);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList1: "
                           + ArrLis1);

        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis2
            = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis2.add(10);
        ArrLis2.add(66);
        ArrLis2.add(97);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList2: "
                           + ArrLis2);

        // Applying the function
        ArrLis2.retainAll(ArrLis1);

        // print CopyOnWriteArrayLists

        System.out.println("After applying retainAll()"
                           + " method on ArrLis2");
        System.out.println("CopyOnWriteArrayList1: "
                           + ArrLis1);
        System.out.println("CopyOnWriteArrayList2: "
                           + ArrLis2);
    }
}
```

**Output:**

```java
CopyOnWriteArrayList1: [34, 66, 72, 10]
CopyOnWriteArrayList2: [10, 66, 97]
After applying retainAll() method on ArrLis2
CopyOnWriteArrayList1: [34, 66, 72, 10]
CopyOnWriteArrayList2: [10, 66]

```

**程序 2:** 该程序涉及字符串类型的 CopyOnArraylist retainAll()方法:

```java
// Java Program to illustrate CopyOnArrayList
// retainAll() method

import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        CopyOnWriteArrayList<String> ArrLis1
            = new CopyOnWriteArrayList<String>();

        // Add elements
        ArrLis1.add("geeks");
        ArrLis1.add("shaan");
        ArrLis1.add("gfg");
        ArrLis1.add("programming");

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList1: "
                           + ArrLis1);

        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<String> ArrLis2
            = new CopyOnWriteArrayList<String>();

        // Add elements
        ArrLis2.add("geeks");
        ArrLis2.add("gfg");
        ArrLis2.add("qwe");

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList2: "
                           + ArrLis2);

        // Applying the function
        ArrLis2.retainAll(ArrLis1);

        // print CopyOnWriteArrayLists

        System.out.println("After applying retainAll()"
                           + " method on ArrLis2");
        System.out.println("CopyOnWriteArrayList1: "
                           + ArrLis1);
        System.out.println("CopyOnWriteArrayList2: "
                           + ArrLis2);
    }
}
```

**Output:**

```java
CopyOnWriteArrayList1: [geeks, shaan, gfg, programming]
CopyOnWriteArrayList2: [geeks, gfg, qwe]
After applying retainAll() method on ArrLis2
CopyOnWriteArrayList1: [geeks, shaan, gfg, programming]
CopyOnWriteArrayList2: [geeks, gfg]

```