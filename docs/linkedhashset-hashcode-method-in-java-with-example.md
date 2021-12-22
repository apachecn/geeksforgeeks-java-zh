# 用示例

链接 Java 中的 hashCode()方法

> 原文:[https://www . geeksforgeeks . org/link edhashset-hashcode-method-in-Java-with-example/](https://www.geeksforgeeks.org/linkedhashset-hashcode-method-in-java-with-example/)

Java 中 **LinkedHashSet** 的 **hashCode()** 方法用于获取 LinkedHashSet 这个实例的 hashCode 值。它返回一个整数值，该整数值是 LinkedHashSet 实例的 hashCode 值。

**语法:**

```
public int hashCode()
```

**参数:**该功能没有参数。

**返回:**该方法返回一个**整数值**，这是 LinkedHashSet 实例的 hashCode 值。

以下示例说明了 LinkedHashSet.hashCode()方法:

**例 1:**

```
// Java code to demonstrate the working of
// hashCode() method in LinkedHashSet

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an LinkedHashSet
        LinkedHashSet<Integer> LHS
            = new LinkedHashSet<Integer>();

        // using add() to initialize values
        // [1, 2, 3, 4]
        LHS.add(1);
        LHS.add(2);
        LHS.add(3);
        LHS.add(4);

        // print LinkedHashSet
        System.out.println("LinkedHashSet: "
                           + LHS);

        // Get the hashCode value
        // using hashCode() value
        System.out.println("HashCode value: "
                           + LHS.hashCode());
    }
}
```

**Output:**

```
LinkedHashSet: [1, 2, 3, 4]
HashCode value: 10

```

**例 2:**

```
// Java code to demonstrate the working of
// hashCode() method in LinkedHashSet

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an LinkedHashSet
        LinkedHashSet<String> LHS
            = new LinkedHashSet<String>();

        // using add() to initialize values
        // [Geeks, For, ForGeeks, GeeksForGeeks]
        LHS.add("Geeks");
        LHS.add("For");
        LHS.add("ForGeeks");
        LHS.add("GeeksForGeeks");

        // print LinkedHashSet
        System.out.println("LinkedHashSet: "
                           + LHS);

        // Get the hashCode value
        // using hashCode() value
        System.out.println("HashCode value: "
                           + LHS.hashCode());
    }
}
```

**Output:**

```
LinkedHashSet: [Geeks, For, ForGeeks, GeeksForGeeks]
HashCode value: -482506029

```