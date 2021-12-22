# 用示例

在 Java 中抽象设置 clear()方法

> 原文:[https://www . geesforgeks . org/abstract set-clear-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractset-clear-method-in-java-with-example/)

Java 中**抽象集**的 **clear()** 方法用于移除一个集合中的所有元素。此调用返回后，集合将为空。

**语法:**

```java
public void clear()
```

**参数:**此功能无参数。

**返回:**该方法不返回值。它会移除集合中的所有元素并使其为空。

下面的例子说明了 AbstractSet.clear()方法:

**例 1:**

```java
// Java code to demonstrate the working of
// clear() method in AbstractSet

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an AbstractSet
        AbstractSet<Integer> arr
            = new TreeSet<Integer>();

        // using add() to initialize values
        // [1, 2, 3, 4]
        arr.add(1);
        arr.add(2);
        arr.add(3);
        arr.add(4);

        // set initially
        System.out.println("The set initially: "
                           + arr);

        // clear function used
        arr.clear();

        // set after clearing all elements
        System.out.println("The set after "
                           + "using clear() method: "
                           + arr);
    }
}
```

**Output:**

```java
The set initially: [1, 2, 3, 4]
The set after using clear() method: []

```

**例 2:**

```java
// Java code to demonstrate the working of
// clear() method in AbstractSet

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an AbstractSet
        AbstractSet<String> arr
            = new TreeSet<String>();

        // using add() to initialize values
        // [Geeks, For, ForGeeks, GeeksForGeeks]
        arr.add("Geeks");
        arr.add("For");
        arr.add("ForGeeks");
        arr.add("GeeksForGeeks");

        // set initially
        System.out.println("The set initially: "
                           + arr);

        // clear function used
        arr.clear();

        // set after clearing all elements
        System.out.println("The set after "
                           + "using clear() method: "
                           + arr);
    }
}
```

**Output:**

```java
The set initially: [For, ForGeeks, Geeks, GeeksForGeeks]
The set after using clear() method: []

```