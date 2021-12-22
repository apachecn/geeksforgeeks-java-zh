# 抽象用示例

设置 Java 中的 Array(T[])方法

> 原文:[https://www . geesforgeks . org/abstract set-to arrayt-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractset-toarrayt-method-in-java-with-example/)

Java 中**抽象集类**的 **toArray(T[])** 方法方法用于形成与抽象集相同元素的数组。它以正确的顺序返回包含这个抽象集中所有元素的数组**；**返回数组的运行时类型是指定数组的运行时类型。如果抽象集适合指定的数组，它将在其中返回。否则，将使用指定数组的运行时类型和此抽象集的大小来分配新数组。
如果抽象集适合指定的数组，并且有剩余空间(即数组中的元素比抽象集多)，数组中紧跟抽象集末尾的元素将被设置为空。(只有当调用方知道抽象集不包含任何空元素时，这在确定抽象集的长度时才有用。)

**语法:**

```java
public <T> T[] toArray(T[] a)
```

**参数:**该方法接受一个参数 **arr[]** ，如果抽象集的元素足够大，则该参数是要存储到其中的数组；否则，将为此目的分配一个相同运行时类型的新数组。

**返回值:**该方法返回一个包含与抽象集相似元素的数组。

**异常:**该方法可能会引发两种类型的异常:

*   **arraystorexception**:当提到的数组属于不同类型，无法与抽象集中提到的元素进行比较时。
*   **NullPointerException** :如果数组为 Null，那么抛出这个异常。

下面的程序说明了 AbstractSet.toArray(arr[])方法的工作原理。

**程序 1:** 当数组具有抽象集的大小时

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class AbstractSetDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractSet
        AbstractSet<String>
            abs_col = new TreeSet<String>();

        // Use add() method to add
        // elements into the AbstractSet
        abs_col.add("Welcome");
        abs_col.add("To");
        abs_col.add("Geeks");
        abs_col.add("For");
        abs_col.add("Geeks");

        // Displaying the AbstractSet
        System.out.println("The AbstractSet: "
                           + abs_col);

        // Creating the array and using toArray()
        String[] arr = new String[5];
        arr = abs_col.toArray(arr);

        // Displaying arr
        System.out.println("The arr[] is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The AbstractSet: [For, Geeks, To, Welcome]
The arr[] is:
For
Geeks
To
Welcome
null

```

**程序 2:** 当数组小于抽象集的大小时

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class AbstractSetDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractSet
        AbstractSet<String>
            abs_col = new TreeSet<String>();

        // Use add() method to add
        // elements into the AbstractSet
        abs_col.add("Welcome");
        abs_col.add("To");
        abs_col.add("Geeks");
        abs_col.add("For");
        abs_col.add("Geeks");

        // Displaying the AbstractSet
        System.out.println("The AbstractSet: "
                           + abs_col);

        // Creating the array and using toArray()
        String[] arr = new String[1];
        arr = abs_col.toArray(arr);

        // Displaying arr
        System.out.println("The arr[] is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The AbstractSet: [For, Geeks, To, Welcome]
The arr[] is:
For
Geeks
To
Welcome

```

**程序 3:** 当数组大于抽象集的大小时

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class AbstractSetDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractSet
        AbstractSet<String>
            abs_col = new TreeSet<String>();

        // Use add() method to add
        // elements into the AbstractSet
        abs_col.add("Welcome");
        abs_col.add("To");
        abs_col.add("Geeks");
        abs_col.add("For");
        abs_col.add("Geeks");

        // Displaying the AbstractSet
        System.out.println("The AbstractSet: "
                           + abs_col);

        // Creating the array and using toArray()
        String[] arr = new String[10];
        arr = abs_col.toArray(arr);

        // Displaying arr
        System.out.println("The arr[] is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The AbstractSet: [For, Geeks, To, Welcome]
The arr[] is:
For
Geeks
To
Welcome
null
null
null
null
null
null

```

**程序 4:** 演示空指针异常

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class AbstractSetDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractSet
        AbstractSet<String>
            abs_col = new TreeSet<String>();

        // Use add() method to add
        // elements into the AbstractSet
        abs_col.add("Welcome");
        abs_col.add("To");
        abs_col.add("Geeks");
        abs_col.add("For");
        abs_col.add("Geeks");

        // Displaying the AbstractSet
        System.out.println("The AbstractSet: "
                           + abs_col);

        try {
            // Creating the array
            String[] arr = null;
            // using toArray()
            // Since arr is null
            // Hence exception will be thrown
            arr = abs_col.toArray(arr);

            // Displaying arr
            System.out.println("The arr[] is:");
            for (int j = 0; j < arr.length; j++)
                System.out.println(arr[j]);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
The AbstractSet: [For, Geeks, To, Welcome]
Exception: java.lang.NullPointerException

```