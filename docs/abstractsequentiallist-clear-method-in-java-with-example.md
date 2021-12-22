# Java 中的抽象顺序列表清除()方法，示例

> 原文:[https://www . geesforgeks . org/abstractsequentialist-clear-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractsequentiallist-clear-method-in-java-with-example/)

Java 中**抽象顺序列表**的 **clear()** 方法用于移除列表中的所有元素。该呼叫返回后，列表将为空。

**语法:**

```
public void clear()
```

**参数:**该功能没有参数。

**返回:**该方法不返回值。它删除列表中的所有元素，并使其为空。

以下示例说明了 AbstractSequentialList.clear()方法:

**例 1:**

```
// Java code to demonstrate the working of
// clear() method in AbstractSequentialList

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

        // list initially
        System.out.println("The list initially: "
                           + arr);

        // clear function used
        arr.clear();

        // list after clearing all elements
        System.out.println("The list after "
                           + "using clear() method: "
                           + arr);
    }
}
```

**Output:**

```
The list initially: [1, 2, 3, 4]
The list after using clear() method: []

```

**例 2:**

```
// Java code to demonstrate the working of
// clear() method in AbstractSequentialList

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

        // list initially
        System.out.println("The list initially: "
                           + arr);

        // clear function used
        arr.clear();

        // list after clearing all elements
        System.out.println("The list after "
                           + "using clear() method: "
                           + arr);
    }
}
```

**Output:**

```
The list initially: [Geeks, For, ForGeeks, GeeksForGeeks]
The list after using clear() method: []

```