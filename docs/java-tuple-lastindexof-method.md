# JavaTuple lastIndexOf()方法

> 原文:[https://www . geesforgeks . org/Java-tuple-last indexof-method/](https://www.geeksforgeeks.org/java-tuple-lastindexof-method/)

[组织. javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的 **lastIndexOf()** 方法用于在 TupleClass 中查找作为参数传递的值的最后一个索引。此方法采用对象类型的参数，因此它可以检查所有类型的值。它继承自 JavaTuple 类。这个方法可以用于 javatuples 库的任何元组类对象。如果多次找到，它将返回一个 int，这是作为参数传递的值的最后一个索引。如果只找到一次，它将返回该索引。如果没有找到，则返回-1。

**方法申报:**

```java
public final int lastIndexOf(Object value)
```

**语法:**

```java
int index = TupleClassObject.lastIndexOf(Object value)
```

这里 **TupleClassObject** 代表像 Unit、Quintet、Decade 等使用的 JavaTuple 类对象。

**返回值:**如果多次找到，该方法返回一个 int，它是作为参数传递的值的最后一个索引。如果只找到一次，它将返回该索引。如果没有找到，则返回-1。

下面是一些程序，它们将说明使用 lastIndexOf()方法的各种方法:

**程序 1:** 使用 lastIndexOf()与单位类:

```java
// Below is a Java program to use lastIndexOf() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        // Creating an Unit with one value
        Unit<String> unit = Unit.with("GeeksforGeeks");

        // Using lastIndexOf() method for present value
        int index = unit.lastIndexOf("GeeksforGeeks");

        // Printing the index
        System.out.println("Last Index of GeeksforGeeks = "
                           + index);

        // Using lastIndexOf() method for absent value
        index = unit.lastIndexOf("Present");

        // Printing the index
        System.out.println("Last Index of Present = "
                           + index);
    }
}
```

**输出:**

```java
Last Index of GeeksforGeeks = 0
Last Index of Present = -1
```

**程序 2:** 使用 lastIndexOf()搭配四重奏类:

```java
// Below is a Java program to use lastIndexOf() method

import java.util.*;
import org.javatuples.Quartet;

class GfG {
    public static void main(String[] args)
    {
        // Creating a quartet
        Quartet<Integer, Integer, Integer, String> quartet
            = Quartet.with(Integer.valueOf(1),
                           Integer.valueOf(1),
                           Integer.valueOf(1),
                           "GeeksforGeeks");

        // Using lastIndexOf() method for value
        // present more than once
        int index = quartet.lastIndexOf(1);

        // Printing the index
        System.out.println("Last Index of 1 = "
                           + index);

        // Using lastIndexOf() method for value
        // present just once
        index = quartet.lastIndexOf("GeeksforGeeks");

        // Printing the index
        System.out.println("Last Index of GeeksforGeeks = "
                           + index);

        // Using lastIndexOf() method for value
        // not present
        index = quartet.lastIndexOf(20.5);

        // Printing the index
        System.out.println("Last Index of 20.5 = "
                           + index);
    }
}
```

**输出:**

```java
Last Index of 1 = 2
Last Index of GeeksforGeeks = 3
Last Index of 20.5 = -1
```

**注意:**同样，它也可以用于任何其他 JavaTuple 类。