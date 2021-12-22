# 用示例

在 Java 中抽象设置 size()方法

> 原文:[https://www . geesforgeks . org/abstract set-size-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractset-size-method-in-java-with-example/)

Java 中**抽象集**的 **size()** 方法用于获取抽象集的这个实例的大小。它返回一个整数值，这是抽象集实例的大小。

**语法:**

```
public int size()
```

**参数:**该功能没有参数。

**返回:**该方法返回一个**整数值**，这是抽象集实例的大小。

以下示例说明了 AbstractSet.size()方法:

**例 1:**

```
// Java code to demonstrate the working of
// size() method in AbstractSet

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

        // print AbstractSet
        System.out.println("AbstractSet: "
                           + arr);

        // Get the size
        // using size()
        System.out.println("Size: "
                           + arr.size());
    }
}
```

**Output:**

```
AbstractSet: [1, 2, 3, 4]
Size: 4

```

**例 2:**

```
// Java code to demonstrate the working of
// size() method in AbstractSet

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

        // print AbstractSet
        System.out.println("AbstractSet: "
                           + arr);

        // Get the size
        // using size()
        System.out.println("Size: "
                           + arr.size());
    }
}
```

**Output:**

```
AbstractSet: [For, ForGeeks, Geeks, GeeksForGeeks]
Size: 4

```