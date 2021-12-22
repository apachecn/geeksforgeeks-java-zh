# 用示例

在 Java 中设置数组(T[])方法

> 原文:[https://www . geesforgeks . org/hashset-to array t-Java 中的方法-示例/](https://www.geeksforgeeks.org/hashset-toarrayt-method-in-java-with-example/)

Java 中 **HashSet 类**的 **toArray(T[])** 方法方法用于形成一个与 HashSet 相同元素的数组。它返回一个数组，包含这个哈希集中所有元素的正确顺序**；**返回数组的运行时类型是指定数组的运行时类型。如果 HashSet 适合指定的数组，它将在其中返回。否则，将使用指定数组的运行时类型和该哈希集的大小分配一个新数组。
如果 HashSet 适合指定的数组，并且有多余的空间(即数组中的元素比 HashSet 多)，数组中紧接 HashSet 末尾的元素将被设置为空。(只有当调用者知道 HashSet 不包含任何空元素时，这在确定 HashSet 的长度时才有用。)

**语法:**

```java
public <T> T[] toArray(T[] a)
```

**参数:**该方法接受一个参数 **arr[]** ，如果数组足够大，则该参数是存储哈希集元素的数组；否则，将为此目的分配一个相同运行时类型的新数组。

**返回值:**该方法返回一个数组，该数组包含与 HashSet 类似的元素。

**异常:**该方法可能会引发两种类型的异常:

*   **arraystorexception**:当提到的数组属于不同类型，无法与 HashSet 中提到的元素进行比较时。
*   **NullPointerException** :如果数组为 Null，那么抛出这个异常。

下面的程序说明了 HashSet.toArray(arr[])方法的工作原理。

**程序 1:** 当数组的大小为 HashSet 时

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class HashSetDemo {
    public static void main(String args[])
    {
        // Creating an empty HashSet
        HashSet<String>
            hashSet = new HashSet<String>();

        // Use add() method to add
        // elements into the HashSet
        hashSet.add("Welcome");
        hashSet.add("To");
        hashSet.add("Geeks");
        hashSet.add("For");
        hashSet.add("Geeks");

        // Displaying the HashSet
        System.out.println("The HashSet: "
                           + hashSet);

        // Creating the array and using toArray()
        String[] arr = new String[5];
        arr = hashSet.toArray(arr);

        // Displaying arr
        System.out.println("The arr[] is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The HashSet: [Geeks, For, Welcome, To]
The arr[] is:
Geeks
For
Welcome
To
null

```

**程序 2:** 当数组小于 HashSet 的大小时

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class HashSetDemo {
    public static void main(String args[])
    {
        // Creating an empty HashSet
        HashSet<String>
            hashSet = new HashSet<String>();

        // Use add() method to add
        // elements into the HashSet
        hashSet.add("Welcome");
        hashSet.add("To");
        hashSet.add("Geeks");
        hashSet.add("For");
        hashSet.add("Geeks");

        // Displaying the HashSet
        System.out.println("The HashSet: "
                           + hashSet);

        // Creating the array and using toArray()
        String[] arr = new String[1];
        arr = hashSet.toArray(arr);

        // Displaying arr
        System.out.println("The arr[] is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The HashSet: [Geeks, For, Welcome, To]
The arr[] is:
Geeks
For
Welcome
To

```

**程序 3:** 当数组大于 HashSet 的大小时

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class HashSetDemo {
    public static void main(String args[])
    {
        // Creating an empty HashSet
        HashSet<String>
            hashSet = new HashSet<String>();

        // Use add() method to add
        // elements into the HashSet
        hashSet.add("Welcome");
        hashSet.add("To");
        hashSet.add("Geeks");
        hashSet.add("For");
        hashSet.add("Geeks");

        // Displaying the HashSet
        System.out.println("The HashSet: "
                           + hashSet);

        // Creating the array and using toArray()
        String[] arr = new String[10];
        arr = hashSet.toArray(arr);

        // Displaying arr
        System.out.println("The arr[] is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The HashSet: [Geeks, For, Welcome, To]
The arr[] is:
Geeks
For
Welcome
To
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

public class HashSetDemo {
    public static void main(String args[])
    {
        // Creating an empty HashSet
        HashSet<String>
            hashSet = new HashSet<String>();

        // Use add() method to add
        // elements into the HashSet
        hashSet.add("Welcome");
        hashSet.add("To");
        hashSet.add("Geeks");
        hashSet.add("For");
        hashSet.add("Geeks");

        // Displaying the HashSet
        System.out.println("The HashSet: "
                           + hashSet);

        try {
            // Creating the array
            String[] arr = null;
            // using toArray()
            // Since arr is null
            // Hence exception will be thrown
            arr = hashSet.toArray(arr);

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
The HashSet: [Geeks, For, Welcome, To]
Exception: java.lang.NullPointerException

```