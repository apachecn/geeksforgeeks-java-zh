# Java 中的 copy onwriterarraylist addallbsent()方法，带示例

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-addallabsent-method-in-Java-with-examples/](https://www.geeksforgeeks.org/copyonwritearraylist-addallabsent-method-in-java-with-examples/)

**[copy onwriterarraylist](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)**的**addallbsent(E E)**方法按照指定集合的迭代器返回元素的顺序，将指定集合中尚未包含在该列表中的所有元素追加到该列表的末尾。

**语法:**

```
public int addAllAbsent(Collection<E> collection)
```

**参数:**该函数接受单个强制参数**集合**，该集合指定了列表中不存在的集合。

**返回值:**该函数返回*一个整数值*，如果列表中添加了元素，则该值为数字。

**异常:**如果指定的集合为空，该方法抛出**空指针异常**。

下面的程序说明了 addAllAbsent()函数:

**程序 1:**

```
// Java Program to illustrate the CopyOnWriteArrayList
// addAllAbsent() method in Java

import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis
            = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis.add(2);
        ArrLis.add(3);
        ArrLis.add(4);
        ArrLis.add(7);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: "
                           + ArrLis);

        // creating an Empty Integer ArrayList
        ArrayList<Integer> arr = new ArrayList<Integer>(4);

        // using add() to initialize values
        // [1, 2, 3, 4]
        arr.add(1);
        arr.add(2);
        arr.add(3);
        arr.add(4);

        // list initially
        System.out.println("The collection to be appended: "
                           + arr);

        // Append the list arr in the list ArrLis
        // using addAllAbsent() method
        System.out.println("\nNumber of elements appended"
                           + " using addAllAbsent() method: "
                           + ArrLis.addAllAbsent(arr));

        // print CopyOnWriteArrayList
        System.out.println("Modified CopyOnWriteArrayList: "
                           + ArrLis);
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [2, 3, 4, 7]
The collection to be appended: [1, 2, 3, 4]

Number of elements appended using addAllAbsent() method: 1
Modified CopyOnWriteArrayList: [2, 3, 4, 7, 1]

```

**程序 2:** 演示 NullPointerException

```
// Java Program to illustrate the CopyOnWriteArrayList
// addAllAbsent() method in Java

import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis
            = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis.add(2);
        ArrLis.add(3);
        ArrLis.add(4);
        ArrLis.add(7);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: "
                           + ArrLis);

        // creating a null Integer ArrayList
        ArrayList<Integer> arr = null;

        // list initially
        System.out.println("The collection to be appended: "
                           + arr);

        try {
            // Append the list arr in the list ArrLis
            // using addAllAbsent() method
            System.out.println("\nTrying to append null collection\n");
            ArrLis.addAllAbsent(arr);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
CopyOnWriteArrayList: [2, 3, 4, 7]
The collection to be appended: null

Trying to append null collection

java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/concurrent/copyonwriterarylist . html # addAllAbsent-Java . util . collection-](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#addAllAbsent-java.util.Collection)