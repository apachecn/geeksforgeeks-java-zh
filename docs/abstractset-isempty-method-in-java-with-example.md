# 用示例

在 Java 中抽象设置 isEmpty()方法

> 原文:[https://www . geesforgeks . org/abstract set-isempty-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractset-isempty-method-in-java-with-example/)

Java 中**抽象集**的 **isEmpty()** 方法用来检查这个抽象集是否为空。它返回一个布尔值，表示相同的内容。

**语法:**

```
public boolean isEmpty()
```

**参数:**此功能无参数。

**返回:**该方法返回一个**布尔值**，表示抽象集的这个实例是否为空。

以下示例说明了 AbstractSet.isEmpty()方法:

**例 1:**

```
// Java code to demonstrate the working of
// isEmpty() method in AbstractSet

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

        // Check if AbstractSet is empty
        // using isEmpty() value
        System.out.println("Is AbstractSet empty? "
                           + arr.isEmpty());
    }
}
```

**Output:**

```
AbstractSet: [1, 2, 3, 4]
Is AbstractSet empty? false

```

**例 2:**

```
// Java code to demonstrate the working of
// isEmpty() method in AbstractSet

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an AbstractSet
        AbstractSet<String> arr
            = new TreeSet<String>();

        // print AbstractSet
        System.out.println("AbstractSet: "
                           + arr);

        // Check if AbstractSet is empty
        // using isEmpty() value
        System.out.println("Is AbstractSet empty? "
                           + arr.isEmpty());
    }
}
```

**Output:**

```
AbstractSet: []
Is AbstractSet empty? true

```