# Java 中的 CopyOnWriteArraySet isEmpty()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarrayset-isempty-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearrayset-isempty-method-in-java/)

**是 [**的空方法**](https://www.geeksforgeeks.org/copyonwritearrayset-in-java/) 检查集合是否为空。如果集合为空，则返回真，否则返回假。**

**语法:**

```java
public boolean isEmpty()
```

**返回值:**如果集合为空，则函数返回*真*，否则返回*假。*

以下程序说明了上述功能:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate the
// isEmpty() method in CopyOnWriteArraySet

import java.util.concurrent.CopyOnWriteArraySet;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<Integer> ArrSet
            = new CopyOnWriteArraySet<Integer>();

        // Add elements
        ArrSet.add(32);
        ArrSet.add(67);
        ArrSet.add(98);
        ArrSet.add(100);

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: " + ArrSet);

        // check using function
        if (ArrSet.isEmpty())
            System.out.println("\nSet is empty");
        else
            System.out.println("\nSet is not empty");
    }
}
```

**Output:** 

```java
CopyOnWriteArraySet: [32, 67, 98, 100]

Set is not empty
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate the
// isEmpty() method in CopyOnWriteArraySet
import java.util.concurrent.CopyOnWriteArraySet;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<String> ArrSet
            = new CopyOnWriteArraySet<String>();

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

        // check using function
        if (ArrSet.isEmpty())
            System.out.println("\nSet is empty");
        else
            System.out.println("\nSet is not empty");
    }
}
```

**Output:** 

```java
CopyOnWriteArraySet: []

Set is empty
```

**参考:**T2【https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copy onwriterarrayset . html # isEmpty–T4】