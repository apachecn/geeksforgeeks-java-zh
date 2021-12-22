# Java 中的 CopyOnWriteArrayList remove()方法，示例

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-remove-method-in-Java-with-examples/](https://www.geeksforgeeks.org/copyonwritearraylist-remove-method-in-java-with-examples/)

Java 中**copy onarraylist**的 **remove()** 方法用于移除列表中的元素。

**语法:**

```java
1\. public E remove(int index)
2\. public boolean remove(Object o)

```

### 1.移除(整数索引)

Java 中 CopyOnArrayList 的 **remove(int index)** 方法用于移除列表中指定位置的元素。

**语法:**

```java
public E remove(int index)

```

**参数:**该方法接受指定元素位置的强制参数索引。

**返回类型:**该方法删除指定元素后返回列表。

**异常:**如果指定的索引超出范围，即索引小于 0 或大于或等于列表的大小，此方法将引发 ArrayIndexOutOfBounds 异常。

下面的程序说明了 Java 中 CopyOnArrayList 的移除(int index)方法:

**程序 1:** 该程序涉及整数类型

```java
// Java Program to illustrate CopyOnArrayList
// remove(int index) method

import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        CopyOnWriteArrayList<Integer> ArrLis1
            = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis1.add(63);
        ArrLis1.add(54);
        ArrLis1.add(81);
        ArrLis1.add(96);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: "
                           + ArrLis1);

        ArrLis1.remove(2);
        // check using function
        System.out.println(ArrLis1);
    }
}
```

**的 CopyOnArrayList remove(int index)输出:**

```java
CopyOnWriteArrayList: [63, 54, 81, 96]
[63, 54, 96]

```

**程序 2:** 该程序涉及字符串类型

```java
// Java Program to illustrate CopyOnArrayList
// remove(int index) method

import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        CopyOnWriteArrayList<String> ArrLis1
            = new CopyOnWriteArrayList<String>();

        // Add elements
        ArrLis1.add("geeks");
        ArrLis1.add("gfg");
        ArrLis1.add("programming");

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: "
                           + ArrLis1);

        ArrLis1.remove(0);
        // check using function
        System.out.println(ArrLis1);
    }
}
```

**的 CopyOnArrayList 移除(int index)输出:**

```java
CopyOnWriteArrayList: [geeks, gfg, programming]
[gfg, programming]

```