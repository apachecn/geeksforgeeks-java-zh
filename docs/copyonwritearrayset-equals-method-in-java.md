# Java 中的 CopyOnWriteArraySet 等于()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarrayset-equals-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearrayset-equals-method-in-java/)

[**copy onwriterarrayset**](https://www.geeksforgeeks.org/copyonwritearrayset-in-java/)的 **equals(对象 0)**方法将指定的对象与该集合进行相等比较。如果指定的对象与此对象是同一个对象，或者它也是一个集合，并且迭代器在指定集合上返回的元素与迭代器在此集合上返回的元素相同，则返回 true。更正式地说，如果两个迭代器返回相同数量的元素，则认为它们返回相同的元素，对于迭代器在指定集合上返回的每个元素 e1，迭代器在该集合上返回一个元素 e2，这样(e1==null？e2==null : e1.equals(e2))。

**语法:**

```java
public boolean equals(Object O)
```

**参数:**该函数接受一个强制参数对象 **O** ，该对象是要与复制写数组进行比较的对象。

**返回值:**如果被比较对象等于该集合，则函数返回*真*。

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate the
// equals() method in CopyOnWriteArraySet

import java.util.concurrent.CopyOnWriteArraySet;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<Integer> ArrSet1
            = new CopyOnWriteArraySet<Integer>();

        // Add elements
        ArrSet1.add(32);
        ArrSet1.add(67);
        ArrSet1.add(98);
        ArrSet1.add(100);

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet 1: "
                           + ArrSet1);

        // create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<Integer> ArrSet2
            = new CopyOnWriteArraySet<Integer>();

        // Add elements
        ArrSet2.add(32);
        ArrSet2.add(67);
        ArrSet2.add(98);
        ArrSet2.add(100);

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet 2: "
                           + ArrSet2);

        // compares both using equal() function
        if (ArrSet1.equals(ArrSet2))
            System.out.println("Both are Equal");
        else
            System.out.println("Both are not Equal");
    }
}
```

**Output:** 

```java
CopyOnWriteArraySet 1: [32, 67, 98, 100]
CopyOnWriteArraySet 2: [32, 67, 98, 100]
Both are Equal
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate the
// equals() method in CopyOnWriteArraySet

import java.util.concurrent.CopyOnWriteArraySet;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<Integer> ArrSet1
            = new CopyOnWriteArraySet<Integer>();

        // Add elements
        ArrSet1.add(32);
        ArrSet1.add(67);
        ArrSet1.add(98);
        ArrSet1.add(100);

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet 1: "
                           + ArrSet1);

        // create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<Integer> ArrSet2
            = new CopyOnWriteArraySet<Integer>();

        // Add elements
        ArrSet2.add(3);
        ArrSet2.add(6);
        ArrSet2.add(9);
        ArrSet2.add(10);

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet 2: "
                           + ArrSet2);

        // compares both using equal() function
        if (ArrSet1.equals(ArrSet2))
            System.out.println("Both are Equal");
        else
            System.out.println("Both are not Equal");
    }
}
```

**Output:** 

```java
CopyOnWriteArraySet 1: [32, 67, 98, 100]
CopyOnWriteArraySet 2: [3, 6, 9, 10]
Both are not Equal
```

**参考:**T2【https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copyonwriteraryset . html # equals-Java . lang . object-T4】