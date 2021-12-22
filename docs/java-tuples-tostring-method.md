# JavaTuples toString()方法

> 原文:[https://www.geeksforgeeks.org/java-tuples-tostring-method/](https://www.geeksforgeeks.org/java-tuples-tostring-method/)

[组织. javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的 **toString()** 方法用于将 TupleClass 中的值转换为字符串。这个方法是从 JavaTuple 类继承的。这个方法可以用于 javatuples 库的任何元组类对象。它返回一个由 TupleClassObject 中的值组成的字符串值。

**方法申报:**

```java
public final String toString()
```

**语法:**

```java
String str = TupleClassObject.toString()
```

这里 **TupleClassObject** 代表像 Unit、Quintet、Decade 等使用的 JavaTuple 类对象。

**返回值:**这个方法返回一个包含 TupleClassObject 元素的字符串值，用“，”分隔。

下面的程序说明了使用 toString()方法的各种方法:

**程序 1:** 使用 toString()配合单位类:

```java
// Below is a Java program to use toString() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        // Creating an Unit with one value
        Unit<String> unit = Unit.with("GeeksforGeeks");

        // Using toString() method
        String str = unit.toString();

        System.out.println(str);
    }
}
```

**输出:**

```java
[GeeksforGeeks]
```

**程序二:**使用 toString()配合四方类:

```java
// Below is a Java program to use toString() method

import java.util.*;
import org.javatuples.Quartet;

class GfG {
    public static void main(String[] args)
    {
        // Creating a quartet
        Quartet<Integer, String, String, Double> quartet
            = Quartet.with(Integer.valueOf(1),
                           "GeeksforGeeks",
                           "A computer portal",
                           Double.valueOf(20.18));

        // Using toString() method
        String str = quartet.toString();

        // Printing the String
        System.out.println(str);
    }
}
```

T4】

**输出:**

```java
[1, GeeksforGeeks, A computer portal, 20.18]
```

**注意:**同样，它也可以用于任何其他 JavaTuple 类。