# JavaTuples getValue()方法

> 原文:[https://www.geeksforgeeks.org/java-tuples-getvalue-method/](https://www.geeksforgeeks.org/java-tuples-getvalue-method/)

[org.javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的 **getValue()** 方法用于从作为参数传递的索引中获取 TupleClassObject 的值。这个方法可以用于 javatuples 库的任何元组类对象。它返回一个对象值，该值是作为参数传递的 TupleClassObject 的索引处的元素。由于返回值属于对象类型，因此使用 getValue()会失去类型安全性。

**方法申报:**

```java
public final Object getValue(int pos)
```

**语法:**

```java
Object val = TupleClassObject.getValue(int pos)
```

这里 **TupleClassObject** 代表像 Unit、Quintet、Decade 等使用的 JavaTuple 类对象。

**参数:**该方法以 *pos* 为参数，其中:

*   位置切望元组 ClassObject 魏冄。
*   **图类对象**–表示像单位、五重奏、十年等使用的 JavaTuple 类对象。

**返回值:**该方法返回一个对象值，该对象值是作为参数传递的 TupleClassObject 的索引处的元素。

下面的程序说明了使用 getValue()方法的各种方法:

**程序 1:** 使用 getValue()配合单位类:

```java
// Below is a Java program to use getValue() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        // Creating an Unit with one value
        Unit<String> unit = Unit.with("GeeksforGeeks");

        // Using getValue() method
        Object val = unit.getValue(0);

        System.out.println("Value at 0 = " + val);
    }
}
```

**输出:**

```java
Value at 0 = GeeksforGeeks
```

**程序二:**使用 getValue()配合四方类:

```java
// Below is a Java program to use getValue() method

import java.util.*;
import org.javatuples.Quartet;

class GfG {
    public static void main(String[] args)
    {
        Quartet<String, String, String, String> quartet
            = Quartet.with("GeeksforGeeks",
                           "A computer portal",
                           "for geeks",
                           "by Sandeep Jain");

        // Using getValue() method
        Object val = quartet.getValue(2);

        System.out.println("Value at 2 = " + val);
    }
}
```

**输出:**

```java
Value at 2 = for geeks
```

**注意:**同样，它也可以用于任何其他 JavaTuple 类。