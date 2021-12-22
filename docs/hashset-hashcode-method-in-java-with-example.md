# Java 中的 HashSet hashCode()方法，示例

> 原文:[https://www . geesforgeks . org/hashset-hashcode-method-in-Java-with-example/](https://www.geeksforgeeks.org/hashset-hashcode-method-in-java-with-example/)

Java 中 **HashSet** 的 **hashCode()** 方法用于获取 HashSet 这个实例的 hashCode 值。它返回一个整数值，该整数值是 HashSet 实例的 hashCode 值。

**语法:**

```
public int hashCode()
```

**参数:**该功能没有参数。

**返回:**该方法返回一个**整数值**，该整数值是 HashSet 实例的 hashCode 值。

下面的例子说明了 HashSet.hashCode()方法:

**例 1:**

```
// Java code to demonstrate the working of
// hashCode() method in HashSet

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an HashSet
        HashSet<Integer> arr
            = new HashSet<Integer>();

        // using add() to initialize values
        // [1, 2, 3, 4]
        arr.add(1);
        arr.add(2);
        arr.add(3);
        arr.add(4);

        // print HashSet
        System.out.println("HashSet: "
                           + arr);

        // Get the hashCode value
        // using hashCode() value
        System.out.println("HashCode value: "
                           + arr.hashCode());
    }
}
```

**Output:**

```
HashSet: [1, 2, 3, 4]
HashCode value: 10

```

**例 2:**

```
// Java code to demonstrate the working of
// hashCode() method in HashSet

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an HashSet
        HashSet<String> arr
            = new HashSet<String>();

        // using add() to initialize values
        // [Geeks, For, ForGeeks, GeeksForGeeks]
        arr.add("Geeks");
        arr.add("For");
        arr.add("ForGeeks");
        arr.add("GeeksForGeeks");

        // print HashSet
        System.out.println("HashSet: "
                           + arr);

        // Get the hashCode value
        // using hashCode() value
        System.out.println("HashCode value: "
                           + arr.hashCode());
    }
}
```

**Output:**

```
HashSet: [ForGeeks, Geeks, For, GeeksForGeeks]
HashCode value: -482506029

```