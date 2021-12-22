# Java 中的 CopyOnWriteArraySet add()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarrayset-add-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearrayset-add-method-in-java/)

**[的 **add(E e)** 方法将参数中传递的元素插入到集合的末尾或集合中的指定索引处。向集合中添加新元素时，该函数返回 true。](https://www.geeksforgeeks.org/copyonwritearrayset-in-java/)**

**语法:**

```java
public boolean add(E e)
```

**参数:**该函数接受单个强制参数**元素**，该元素指定要添加到集合中的元素。

**返回值:**该函数在集合中相加时返回*真*。

以下程序说明了上述功能:

**程序 1:**

```java
// Java Program to illustrate the CopyOnWriteArraySet
// add(element) method in Java

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

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

        // 4 is already present hence cannot add
        System.out.println("On adding 4 it returns "
                           + ArrSet.add(4));

        // print CopyOnWriteArraySet
        System.out.println("Updated CopyOnWriteArraySet: "
                           + ArrSet);
    }
}
```

**输出:**

```java
CopyOnWriteArraySet: [2, 3, 4, 7]
On adding 4 it returns false
Updated CopyOnWriteArraySet: [2, 3, 4, 7]

```

**程序二:**

```java
// Java Program to illustrate the CopyOnWriteArraySet
// add(element) method in Java

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
        ArrSet.add(3);
        ArrSet.add(3);

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

        // 45 is not present hence add
        System.out.println("On adding 45 it returns "
                           + ArrSet.add(45));

        // print CopyOnWriteArraySet
        System.out.println("Updated CopyOnWriteArraySet: "
                           + ArrSet);
    }
}
```

**输出:**

```java
CopyOnWriteArraySet: [2, 3]
On adding 45 it returns true
Updated CopyOnWriteArraySet: [2, 3, 45]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copy onwriterarrayset . html # add-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArraySet.html#add-E-)