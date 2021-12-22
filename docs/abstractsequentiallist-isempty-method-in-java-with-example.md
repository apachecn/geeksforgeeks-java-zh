# Java 中的抽象顺序列表 isEmpty()方法，示例

> 原文:[https://www . geeksforgeeks . org/abstractsequentialist-isempty-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractsequentiallist-isempty-method-in-java-with-example/)

Java 中**抽象顺序列表**的 **isEmpty()** 方法用来检查这个抽象顺序列表是否为空。它返回一个布尔值，表示相同的内容。

**语法:**

```java
public boolean isEmpty()
```

**参数:**此功能无参数。

**返回:**该方法返回一个**布尔值**，表示抽象顺序列表的这个实例是否为空。

下面的例子说明了 AbstractSequentialList.isEmpty()方法:

**例 1:**

```java
// Java code to demonstrate the working of
// isEmpty() method in AbstractSequentialList

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

        // Check if AbstractSequentialList is empty
        // using isEmpty() value
        System.out.println("Is AbstractSequentialList empty? "
                           + arr.isEmpty());
    }
}
```

**Output:**

```java
AbstractSequentialList: [1, 2, 3, 4]
Is AbstractSequentialList empty? false

```

**例 2:**

```java
// Java code to demonstrate the working of
// isEmpty() method in AbstractSequentialList

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an AbstractSequentialList
        AbstractSequentialList<String> arr
            = new LinkedList<String>();

        // print AbstractSequentialList
        System.out.println("AbstractSequentialList: "
                           + arr);

        // Check if AbstractSequentialList is empty
        // using isEmpty() value
        System.out.println("Is AbstractSequentialList empty? "
                           + arr.isEmpty());
    }
}
```

**Output:**

```java
AbstractSequentialList: []
Is AbstractSequentialList empty? true

```