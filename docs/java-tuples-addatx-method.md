# JavaTuples addAtX()方法

> 原文:[https://www.geeksforgeeks.org/java-tuples-addatx-method/](https://www.geeksforgeeks.org/java-tuples-addatx-method/)

[org.javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的 **addAtX()** 方法用于在索引 x 处向现有元组添加值。由于 javatuples 是不可变的，因此向现有元组添加值会导致新元组多一个值。例如，向“单位”元组添加一个值会形成“对”元组。这个方法可以用于 javatuples 库的任何元组类对象，除了 Decade 类，因为 Decade 是 JavaTuples 库中可用的最高类。它返回比被调用类高的类的元组类对象，由参数中的值的数量决定。

**语法:**

```java
Triplet<String, Integer, Double> triplet = ...
    ...
Quartet<String, Integer, Double, type(s)> quartet = triplet.addAtX(value(s));
```

**参数:**该方法可以将 *n 个值*作为参数，其中:

*   **x** -The index that represents the value to be added.
*   **n** –Indicates the number of values based on the *class* (unit, equivalent) to be created as the return object.
*   **Type** –Indicates the type of value passed as a parameter.
*   **Value** -Indicates the value passed as a parameter.

**返回值:**这个方法返回 *TupleClass* 的对象，被调用元组类的组合值和作为参数传递的值。传递的值被添加到被称为元组类值的索引 X 处。

下面的程序说明了使用 addAtX()方法的各种方法:

**程序 1:** 当 addAtX()方法用于从 Unit 到 Ennead 的任何类时，直接值作为参数:

```java
// Below is a Java program to demonstrate
// use of addAtX() method with
// direct value

import java.util.*;
import org.javatuples.Unit;
import org.javatuples.Pair;

class GfG {
    public static void main(String[] args)
    {
        // Using with() method to instantiate unit object
        Unit<String> unit = Unit.with("Geeks");

        // Using addAtX() to create Pair
        Pair<String, String> pair = unit.addAt0("forGeeks");

        System.out.println(pair);
    }
}
```

**输出:**

```java
[forGeeks, Geeks]
```

**程序 2:** 当 addAtX()方法用于从 Unit 到 Ennead 的任何类时，以另一个元组类对象作为参数:

```java
// Below is a Java program to demonstrate
// use of addAtX() method with
// multiple value

import java.util.*;
import org.javatuples.Unit;
import org.javatuples.Pair;

class GfG {
    public static void main(String[] args)
    {
        // Using with() method to instantiate unit object
        Unit<String> unit1 = Unit.with("Geeks");

        // Using with() method to instantiate unit object
        Unit<String> unit2 = Unit.with("forGeeks");

        // Using addAtX() to create Pair
        Pair<String, String> pair = unit1.addAt0(unit2);

        System.out.println(pair);
    }
}
```

**输出:**

```java
[forGeeks, Geeks]
```

**注意:**同样，它也可以用于任何其他 JavaTuple 类。