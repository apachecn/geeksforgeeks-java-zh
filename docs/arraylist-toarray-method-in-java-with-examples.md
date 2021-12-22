# Java 中 ArrayList toArray()方法示例

> 原文:[https://www . geesforgeks . org/ArrayList-to array-method-in-Java-with-examples/](https://www.geeksforgeeks.org/arraylist-toarray-method-in-java-with-examples/)

**数组列表**的 **toArray()** 方法用于返回一个数组，该数组包含数组列表中所有元素的正确顺序。

**语法:**

```java
public Object[] toArray()
           or
public <T> T[] toArray(T[] a)
```

**参数:**这个方法要么不接受参数，要么取一个数组**T【】a**作为参数，如果足够大的话，这个数组就是要存储列表元素的数组；否则，将为此目的分配一个相同运行时类型的新数组。

**返回值:**该函数返回**一个包含该列表中所有元素的数组**。

**异常:**这个方法的第一个重载没有抛出异常。但是，第二个重载引发以下异常:

*   **arraystorexception**:如果指定数组的运行时类型不是该列表中每个元素的运行时类型的超类型。
*   如果指定的数组为空，则**为空**

下面的程序说明了 ArrayList.toArray()方法:

**程序 1:**

```java
// Java Program to illustrate the
// ArrayList toArray() method in Java

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of ArrayList
        ArrayList<Integer> ArrLis
            = new ArrayList<Integer>();

        // Add elements
        ArrLis.add(32);
        ArrLis.add(67);
        ArrLis.add(98);
        ArrLis.add(100);

        // print ArrayList
        System.out.println("ArrayList: "
                           + ArrLis);

        // Get the array of the elements
        // of the ArrayList
        // using toArray() method
        Object[] arr = ArrLis.toArray();

        System.out.println("Elements of ArrayList"
                           + " as Array: "
                           + Arrays.toString(arr));
    }
}
```

**Output:**

```java
ArrayList: [32, 67, 98, 100]
Elements of ArrayList as Array: [32, 67, 98, 100]

```

**程序 2:**

```java
// Java Program to illustrate the
// ArrayList toArray(T[]) method in Java

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of ArrayList
        ArrayList<Integer> ArrLis
            = new ArrayList<Integer>();

        // Add elements
        ArrLis.add(32);
        ArrLis.add(67);
        ArrLis.add(98);
        ArrLis.add(100);

        // print ArrayList
        System.out.println("ArrayList: "
                           + ArrLis);

        // Get the array of the elements
        // of the ArrayList
        // using toArray(T[]) method
        Integer arr[] = new Integer[ArrLis.size()];
        arr = ArrLis.toArray(arr);

        System.out.println("Elements of ArrayList"
                           + " as Array: "
                           + Arrays.toString(arr));
    }
}
```

**Output:**

```java
ArrayList: [32, 67, 98, 100]
Elements of ArrayList as Array: [32, 67, 98, 100]

```

**参考:**

*   [https://docs . Oracle . com/javase/9/docs/API/Java/util/ArrayList . html # to array–](https://docs.oracle.com/javase/9/docs/api/java/util/ArrayList.html#toArray--)
*   [https://docs . Oracle . com/javase/9/docs/API/Java/util/ArrayList . html # to array-T:A-](https://docs.oracle.com/javase/9/docs/api/java/util/ArrayList.html#toArray-T:A-)