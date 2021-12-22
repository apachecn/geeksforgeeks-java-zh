# JavaTuple toList()方法

> 原文:[https://www.geeksforgeeks.org/java-tuple-tolist-method/](https://www.geeksforgeeks.org/java-tuple-tolist-method/)

[组织. javatuples](https://www.geeksforgeeks.org/javatuples-introduction;/) 中的 **toList()** 方法用于将 TupleClass 中的值转换为 List。此列表属于对象类型，因此它可以接受所有值。它继承自 JavaTuple 类。这个方法可以用于 javatuples 库的任何元组类对象。它返回由 TupleClassObject 中的值组成的列表。

**方法申报:**

```
public final List<Object> toList()
```

**语法:**

```
List<Object> list = TupleClassObject.toList()
```

这里 **TupleClassObject** 代表像 Unit、Quintet、Decade 等使用的 JavaTuple 类对象。

**返回值:**这个方法返回一个由 TupleClassObject 中的值组成的列表。

下面是一些程序，将说明使用 toList()方法的各种方法:

**程序 1:** 使用 toList()和单元类:

```
// Below is a Java program to use toList() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        // Creating an Unit with one value
        Unit<String> unit = Unit.with("GeeksforGeeks");

        // Using toList() method with Object type
        List<Object> objList = unit.toList();

        // Printing the list
        System.out.println(objList);
    }
}
```

**输出:**

```
[GeeksforGeeks]
```

**程序 2:** 使用 toList()配合四重奏类:

```
// Below is a Java program to use toList() method

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

        // Using toList() method with Object type
        List<Object> objList = quartet.toList();

        // Printing the list
        System.out.println(objList);
    }
}
```

**输出:**

```
[, GeeksforGeeks, A computer portal, 20.18]
```

**注意:**同样，它也可以用于任何其他 JavaTuple 类。