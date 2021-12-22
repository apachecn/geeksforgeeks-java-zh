# Java 中的 CopyOnWriteArrayList toArray()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-to array-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearraylist-toarray-method-in-java/)

的 **toArray()** 方法用于返回一个数组，该数组包含以正确顺序排列的 copy onwriterarraylist 中的所有元素。

**语法:**

```
public Object[] toArray()
           or
public <T> T[] toArray(T[] a)
```

**参数:**这个方法要么不接受参数，要么取一个数组**T【】a**作为参数，如果足够大的话，这个数组就是要存储列表元素的数组；否则，将为此目的分配一个相同运行时类型的新数组。

**返回值:**该函数返回**一个包含该列表中所有元素的数组**。

**异常:**这个方法的第一个重载没有抛出异常。但是，第二个重载抛出以下异常:

*   **[ArrayStorException]** : If the runtime type of the specified array is not the supertype of the runtime type of each element in the list.
*   **null pointer exception** If the specified array is empty

下面的程序说明了 copy onwriterarraylist . to array()方法:

**程序 1:**

```
// Java Program to illustrate the
// CopyOnWriteArrayList toArray() method in Java

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
        ArrLis.add(98);
        ArrLis.add(100);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: "
                           + ArrLis);

        // Get the array of the elements
        // of the CopyOnWriteArrayList
        // using toArray() method
        Object[] arr = ArrLis.toArray();

        System.out.println("Elements of CopyOnWriteArrayList"
                           + " as Array: "
                           + Arrays.toString(arr));
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [32, 67, 98, 100]
Elements of CopyOnWriteArrayList as Array: [32, 67, 98, 100]

```

**程序二:**

```
// Java Program to illustrate the
// CopyOnWriteArrayList toArray(T[]) method in Java

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
        ArrLis.add(98);
        ArrLis.add(100);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: "
                           + ArrLis);

        // Get the array of the elements
        // of the CopyOnWriteArrayList
        // using toArray(T[]) method
        Integer arr[] = new Integer[ArrLis.size()];
        arr = ArrLis.toArray(arr);

        System.out.println("Elements of CopyOnWriteArrayList"
                           + " as Array: "
                           + Arrays.toString(arr));
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [32, 67, 98, 100]
Elements of CopyOnWriteArrayList as Array: [32, 67, 98, 100]

```

**参考:**T2【copy onwriterarraylist . to array()文档，[copy onwriterarraylist . to array(T[])文档](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#toArray-T:A-)