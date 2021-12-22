# JavaToPles indexOf()方法

> 原文:[https://www.geeksforgeeks.org/java-tuples-indexof-method/](https://www.geeksforgeeks.org/java-tuples-indexof-method/)

[组织. javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的 **indexOf()** 方法用于在 TupleClass 中查找作为参数传递的值的索引。此方法采用对象类型的参数，因此它可以检查所有类型的值。它继承自 JavaTuple 类。这个方法可以用于 javatuples 库的任何元组类对象。它返回一个 int，这是作为参数传递的值的第一个索引(如果找到的话)。如果没有找到，则返回-1。

**方法申报:**

```
public final int indexOf(Object value)
```

**语法:**

```
int index = TupleClassObject.indexOf(Object value)
```

这里 **TupleClassObject** 代表像 Unit、Quintet、Decade 等使用的 JavaTuple 类对象。

**返回值:**这个方法返回一个 int，它是作为参数传递的值的第一个索引(如果找到的话)。如果没有找到，则返回-1。

下面的程序说明了使用 indexOf()方法的各种方法:

**程序 1:** 使用 indexOf()与单位类:

```
// Below is a Java program to use indexOf() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        // Creating an Unit with one value
        Unit<String> unit = Unit.with("GeeksforGeeks");

        // Using indexOf() method for present value
        int index1 = unit.indexOf("GeeksforGeeks");

        // Printing the index1
        System.out.println("Index of GeeksforGeeks = "
                           + index1);

        // Using indexOf() method for absent value
        int index2 = unit.indexOf("Present");

        // Printing the index2
        System.out.println("Index of Present = "
                           + index2);
    }
}
```

**输出:**

```
Index of GeeksforGeeks = 0
Index of Present = -1
```

**程序 2:** 使用 indexOf()与四方类:

```
// Below is a Java program to use indexOf() method

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

        // Using indexOf() method for present value
        int index1 = quartet.indexOf("GeeksforGeeks");

        // Printing the index1
        System.out.println("Index of GeeksforGeeks = "
                           + index1);

        // Using indexOf() method for absent value
        int index2 = quartet.indexOf(5);

        // Printing the index2
        System.out.println("Index of 5 = "
                           + index2);
    }
}
```

**输出:**

```
Index of GeeksforGeeks = 1
Index of 5 = -1
```

注意:同样，它也可以用于任何其他的 JavaTuple 类。