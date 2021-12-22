# JavaTuples fromArray()方法

> 原文:[https://www.geeksforgeeks.org/java-tuples-fromarray-method/](https://www.geeksforgeeks.org/java-tuples-fromarray-method/)

[org.javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的 **fromArray()** 方法用于以语义优雅的方式实例化元组，数组的值作为参数给出。这个方法可以用于 javatuples 库的任何元组类对象。它是每个 javatuple 类中的一个静态函数，它返回被调用类的 tuple 类对象，其值由数组的相应值初始化。

**方法申报:**

```java
public static <X> TupleClass<X> fromArray(X[] array)
```

**语法:**

```java
TupleClass<X> obj = TupleClass.fromArray(X[] array)
```

**参数:**该方法以*阵*为参数，其中:

*   **X**–表示数组中值的数据类型。
*   **数组**–表示要插入到 TupleClass 中的值的数组。
*   **类类**–代表像单位、五重奏、十年等使用的 JavaTuple 类。

**返回值:**这个方法返回 *TupleClass* 的对象，调用这个方法，数组的值作为参数传递。

下面的程序说明了使用 fromArray()方法的各种方法:

**程序 1:** 使用来自数组()的单位类:

```java
// Below is a Java program to create
// a Unit tuple from fromArray() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        // Creating an array with one value
        String str[] = { "GeeksforGeeks" };

        // Using fromArray() method
        Unit<String> unit = Unit.fromArray(str);

        System.out.println(unit);
    }
}
```

**输出:**

```java
[GeeksforGeeks]
```

**程序 2:** 使用带有十进制类的 fromArray()

**输出:**

```java
[Geeks, for, Geeks, A, Computer, Science, Portal, for, Geeks, RishabhPrabhu]
```

**注意:**同样，它也可以用于任何其他 JavaTuple 类。