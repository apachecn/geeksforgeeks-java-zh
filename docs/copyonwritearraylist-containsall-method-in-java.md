# Java 中的 copy onwriterarraylist contains all()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-contains all-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearraylist-containsall-method-in-java/)

Java 中 CopyOnWriteArrayList 类的 containsAll()方法用于检查此列表是否包含指定集合中的所有元素。所以基本上它是用来检查一个列表是否包含一组元素。

**语法** :

```
boolean containsAll(Collection col)

```

**参数**:该方法接受集合类型的强制参数 col。这是一个集合，需要检查它的元素是否在列表中。

**返回值**:如果集合列中的所有元素都出现在列表中，则该方法返回真，否则返回假。

**异常**:如果指定的集合为空，则方法抛出 NullPointerException。

下面的程序说明了 CopyOnWriteArrayList 类的 containsAll()方法:

**程序 1** :

```
// Java program to illustrate CopyOnWriteArrayList
//  containsAll() method

import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG1 {
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
        System.out.println("CopyOnWriteArrayList1: " + ArrLis1);

        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<String> ArrLis2
            = new CopyOnWriteArrayList<String>();

        // Add elements
        ArrLis2.add("geeks");
        ArrLis2.add("gfg");

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList2: " + ArrLis2);

        // check using function
        if (ArrLis1.containsAll(ArrLis2))
            System.out.println("All list2 elements are present in list1");
        else
            System.out.println("All list2 elements are not present in list1");

        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<String> ArrLis3
            = new CopyOnWriteArrayList<String>();

        // Add elements
        ArrLis3.add("geeks");
        ArrLis3.add("qwe");

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList3: " + ArrLis3);

        // check using function
        if (ArrLis1.containsAll(ArrLis3))
            System.out.println("All list3 elements are present in list1");
        else
            System.out.println("All list3 elements are not present in list1");
    }
}
```

**输出:**

```
CopyOnWriteArrayList1: [geeks, shaan, gfg, programming]
CopyOnWriteArrayList2: [geeks, gfg]
All list2 elements are present in list1
CopyOnWriteArrayList3: [geeks, qwe]
All list3 elements are not present in list1

```

**程序二** :

```
// Java program to illustrate CopyOnWriteArrayList
// containsAll() method

import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG1 {
    public static void main(String[] args)
    {
        CopyOnWriteArrayList<Integer> ArrLis1
            = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis1.add(23);
        ArrLis1.add(65);
        ArrLis1.add(91);
        ArrLis1.add(126);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList1: " + ArrLis1);

        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis2
            = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis2.add(23);
        ArrLis2.add(126);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList2: " + ArrLis2);

        // check using function
        if (ArrLis1.containsAll(ArrLis2))
            System.out.println("All list2 elements are present in list1");
        else
            System.out.println("All list2 elements are not present in list1");

        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<Integer> ArrLis3
            = new CopyOnWriteArrayList<Integer>();

        // Add elements
        ArrLis3.add(23);
        ArrLis3.add(92);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList3: " + ArrLis3);

        // check using function
        if (ArrLis1.containsAll(ArrLis3))
            System.out.println("All list3 elements are present in list1");
        else
            System.out.println("All list3 elements are not present in list1");
    }
}
```

**输出:**

```
CopyOnWriteArrayList1: [23, 65, 91, 126]
CopyOnWriteArrayList2: [23, 126]
All list2 elements are present in list1
CopyOnWriteArrayList3: [23, 92]
All list3 elements are not present in list1

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/copy onwriterarraylist . html # contains all(Java . util . collection)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#containsAll(java.util.Collection))