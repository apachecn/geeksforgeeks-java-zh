# Java 中的 copy onwriterarraylist listIterator()方法

> 原文:[https://www . geesforgeks . org/copy onwriterarraylist-listiterator-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearraylist-listiterator-method-in-java/)

[](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)**的**列表迭代器()**方法以适当的顺序返回列表中元素的列表迭代器。列表迭代器不支持移除、设置或添加方法。**

****语法:****

```
public ListIterator listIterator()
```

****参数:**函数不接受任何参数。**

****返回值:**函数返回列表迭代器，遍历列表中的元素(按正确的顺序)**

**以下程序说明了上述功能:**

****程序 1:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java Program to illustrate the CopyOnWriteArrayList
// listIterator() method in Java
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
        ArrLis.add(67);
        ArrLis.add(100);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: " + ArrLis);

        // Call listIterator() method of
        Iterator iteratorVals = ArrLis.listIterator();

        // Print elements of iterator
        // created from CopyOnWriteArrayList
        System.out.println("The iterator values"
                           + " of CopyOnWriteArrayList are:");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

****Output:** 

```
CopyOnWriteArrayList: [32, 67, 67, 100]
The iterator values of CopyOnWriteArrayList are:
32
67
67
100
```** 

**[**copy onwriterarraylist**](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)的**列表迭代器(索引)**方法从特定索引开始，以适当的顺序返回列表中元素的列表迭代器。列表迭代器不支持移除、设置或添加方法。**

****语法:****

```
public ListIterator listIterator(int index)
```

****参数:**函数接受一个参数*索引*，它指定从列表迭代器返回的第一个元素的索引。**

****返回值:**函数从指定的索引开始(以正确的顺序)返回列表中元素的列表迭代器。**

****异常:**如果指数超出范围，函数将抛出*指数。***

**以下程序说明了上述功能:**

****程序 1:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java Program to illustrate the CopyOnWriteArrayList
// listIterator() method in Java
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<String> ArrLis
            = new CopyOnWriteArrayList<String>();

        // Add elements
        ArrLis.add("gopal");
        ArrLis.add("gfg");
        ArrLis.add("jgec");
        ArrLis.add("sudo");

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: " + ArrLis);

        // Call listIterator() method from 2nd index
        Iterator iteratorVals = ArrLis.listIterator(2);

        // Print elements of iterator
        // created from CopyOnWriteArrayList
        System.out.println("The iterator values"
                           + " of CopyOnWriteArrayList are:");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

****Output:** 

```
CopyOnWriteArrayList: [gopal, gfg, jgec, sudo]
The iterator values of CopyOnWriteArrayList are:
jgec
sudo
```** 

****程序 2** :**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java Program to illustrate the CopyOnWriteArrayList
// listIterator() method in Java, exception
import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArrayList
        CopyOnWriteArrayList<String> ArrLis
            = new CopyOnWriteArrayList<String>();

        // Add elements
        ArrLis.add("gopal");
        ArrLis.add("gfg");
        ArrLis.add("jgec");
        ArrLis.add("sudo");

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: " + ArrLis);

        // Call listIterator() method from 6th index
        // hence exception is returned
        Iterator iteratorVals = ArrLis.listIterator(6);

        // Print elements of iterator
        // created from CopyOnWriteArrayList
        System.out.println("The iterator values"
                           + " of CopyOnWriteArrayList are:");

        // prints the elements using an iterator
        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

****输出:****

```
Exception in thread "main" java.lang.IndexOutOfBoundsException: Index: 6
    at java.util.concurrent.CopyOnWriteArrayList.listIterator(CopyOnWriteArrayList.java:1107)
    at GFG.main(GFG.java:25)
```

****参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copy onwriterarraylist . html # listIterator–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#listIterator--)**