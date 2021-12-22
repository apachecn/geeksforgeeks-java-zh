# JavaTuple getValueX()方法

> 原文:[https://www.geeksforgeeks.org/javatuple-getvaluex-method/](https://www.geeksforgeeks.org/javatuple-getvaluex-method/)

[org.javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的 **getValueX()** 方法用于从索引 x 中获取 TupleClassObject 的值，该方法可以用于 javatuples 库的任何元组类对象。它返回 TupleClassObject 的索引 X 处的值。返回值的类型是 TupleClassObject 的第 X <super>个</super>元素。因此，与 getValue(X)不同，使用 getValueX()保留了类型安全性。

X 的值从 0 到 TupleClassObject 中存在的元素数量范围减去 1。这意味着对于 Unit 类，X 的可用值为 0。类似地，对于十进制类，X 的可用值是 0、1、2，..数到 9。

**方法申报:**

```
public A getValueX()
```

**语法:**

```
A val = TupleClassObject.getValueX()
```

这里:

*   **TupleClassObject** 表示像单位、五重奏、十年等使用的 JavaTuple 类对象。
*   **A** represents the type of the th element of X
*   **x** represents the index to be taken.

**返回值:**这个方法返回 TupleClassObject 的索引 X 处的值。返回值的类型是图类对象的第 X <super>个</super>元素。

下面是一些程序，将说明使用 getValueX()方法的各种方法:

**程序 1:** 使用 getValueX()配合单位类:

```
// Below is a Java program to use getValueX() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        // Creating an Unit with one value
        Unit<String> unit = Unit.with("GeeksforGeeks");

        // Using getValueX() method for X=0
        // The type of val is String
        // which is the type of the 0th element in Unit
        String val = unit.getValue0();

        System.out.println("Value at 0 = " + val);
    }
}
```

**输出:**

```
Value at 0 = GeeksforGeeks
```

**程序二:**使用 getValueX()配合四方类:

```
// Below is a Java program to use getValueX() method

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

        // Using getValueX() method for X=3
        // The type of val is Double which is the
        // type of the 3rd index value of Quartet
        Double val = quartet.getValue3();

        System.out.println("Value at 3 = " + val);
    }
}
```

T4】

**输出:**

```
Value at 3 = 20.18
```

注意:同样，它也可以用于任何其他的 JavaTuple 类。