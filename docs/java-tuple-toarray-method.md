# JavaTuple toArray()方法

> 原文:[https://www.geeksforgeeks.org/java-tuple-toarray-method/](https://www.geeksforgeeks.org/java-tuple-toarray-method/)

[组织. javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的 **toArray()** 方法用于将 TupleClass 中的值转换为 Object 类型的数组。这个方法是从 JavaTuple 类继承的。这个方法可以用于 javatuples 库的任何元组类对象。它返回一个对象类型数组，该数组由 TupleClassObject 中的值组成。

**方法申报:**

```
public final Object[] toArray()
```

**语法:**

```
Object obj[] = TupleClassObject.toArray()
```

这里 **TupleClassObject** 代表像 Unit、Quintet、Decade 等使用的 JavaTuple 类对象。

**返回值:**该方法返回一个对象类型数组，该数组由 TupleClassObject 中的值组成。

下面是一些程序，将说明使用 toArray()方法的各种方法:

**程序 1:** 使用 toArray()和单元类:

```
// Below is a Java program to use toArray() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        // Creating an Unit with one value
        Unit<String> unit = Unit.with("GeeksforGeeks");

        // Using toArray() method
        Object[] object = unit.toArray();

        // Printing the array elements
        for (Object obj : object) {
            System.out.println(obj);
        }
    }
}
```

**输出:**

```
GeeksforGeeks
```

**程序 2:** 使用 toArray()配合四重奏类:

```
// Below is a Java program to use toArray() method

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

        // Using toArray() method
        Object[] object = unit.toArray();

        // Printing the array elements
        for (Object obj : object) {
            System.out.println(obj);
        }
    }
}
```

**输出:**

```
1
GeeksforGeeks
A computer portal
20.18
```

**注意:**同样，它也可以用于任何其他 JavaTuple 类。