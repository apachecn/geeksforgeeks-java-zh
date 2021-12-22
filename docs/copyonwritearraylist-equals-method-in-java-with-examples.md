# Java 中的 CopyOnWriteArrayList 等于()方法，示例

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/copyonwritearraylist-equals-method-in-java-with-examples/)

**copy onwriterarraylist 等于()**方法用于比较两个列表。它将列表进行比较，因为两个列表应该具有相同的大小，并且两个列表中所有对应的元素对都是相等的。

**语法:**

```java
boolean equals(Object o)
```

**参数:**该函数有一个参数，该参数是要比较是否相等的对象。

**返回:**如果列表相等，该方法返回真。

下面的程序展示了这种方法的实现。

**程序 1:**

```java
// Java code to show the implementation of
// addAll method in list interface

import java.util.*;

public class GfG {

    // Driver code
    public static void main(String[] args)
    {

        // Initializing a list of type Linkedlist
        CopyOnWriteArrayList<Integer> l
            = new CopyOnWriteArrayList<>();
        l.add(10);
        l.add(15);
        l.add(20);
        System.out.println(l);

        // Initializing another list
        CopyOnWriteArrayList<Integer> l2
            = new CopyOnWriteArrayList<Integer>();
        l2.add(100);
        l2.add(200);
        l2.add(300);
        System.out.println(l2);

        if (l.equals(l2))
            System.out.println("Equal");
        else
            System.out.println("Not equal");
    }
}
```

**程序 2:**

```java
// Java code to show the implementation of
// addAll method in list interface

import java.util.*;

public class GfG {

    // Driver code
    public static void main(String[] args)
    {

        // Initializing a list of type Linkedlist
        CopyOnWriteArrayList<Character>
            l = new CopyOnWriteArrayList<Character>();
        l.add('G');
        l.add('E');
        l.add('E');
        l.add('K');
        l.add('S');
        System.out.println(l);

        // Initializing another list
        CopyOnWriteArrayList<Character>
            l2 = new CopyOnWriteArrayList<Character>();
        l2.add('G');
        l2.add('E');
        l2.add('E');
        l2.add('K');
        l2.add('S');
        System.out.println(l2);

        if (l.equals(l2))
            System.out.println("Equal");
        else
            System.out.println("Not equal");
    }
}
```