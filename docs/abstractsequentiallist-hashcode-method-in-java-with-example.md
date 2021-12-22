# Java 中的抽象顺序列表 hashCode()方法，示例

> 原文:[https://www . geesforgeks . org/abstractsequentialist-hashcode-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractsequentiallist-hashcode-method-in-java-with-example/)

Java 中**抽象顺序列表**的 **hashCode()** 方法用来获取抽象顺序列表这个实例的 hashCode 值。它返回一个整数值，该整数值是抽象顺序列表实例的哈希值。

**语法:**

```
public int hashCode()
```

**参数:**该功能没有参数。

**返回:**该方法返回一个**整数值**，这是抽象顺序列表实例的哈希值。

以下示例说明了 abstractsequentialilist . hashcode()方法:

**例 1:**

```
// Java code to demonstrate the working of
// hashCode() method in AbstractSequentialList

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an AbstractSequentialList
        AbstractSequentialList<Integer> arr
            = new LinkedList<Integer>();

        // using add() to initialize values
        // [1, 2, 3, 4]
        arr.add(1);
        arr.add(2);
        arr.add(3);
        arr.add(4);

        // print AbstractSequentialList
        System.out.println("AbstractSequentialList: "
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
AbstractSequentialList: [1, 2, 3, 4]
HashCode value: 955331

```

**例 2:**

```
// Java code to demonstrate the working of
// hashCode() method in AbstractSequentialList

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an AbstractSequentialList
        AbstractSequentialList<String> arr
            = new LinkedList<String>();

        // using add() to initialize values
        // [Geeks, For, ForGeeks, GeeksForGeeks]
        arr.add("Geeks");
        arr.add("For");
        arr.add("ForGeeks");
        arr.add("GeeksForGeeks");

        // print AbstractSequentialList
        System.out.println("AbstractSequentialList: "
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
AbstractSequentialList: [Geeks, For, ForGeeks, GeeksForGeeks]
HashCode value: -927254198

```