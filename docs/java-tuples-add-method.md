# JavaTuples add()方法

> 原文:[https://www.geeksforgeeks.org/java-tuples-add-method/](https://www.geeksforgeeks.org/java-tuples-add-method/)

[org.javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的 **add()** 方法用于向现有元组添加值。由于 JavaTuples 是不可变的，因此向现有的元组添加一个值会导致新的元组多一个值。例如，向“单位”元组添加一个值会形成“对”元组。这个方法可以用于 javatuples 库的任何元组类对象，除了 Decade 类，因为 Decade 是 JavaTuples 库中可用的最高类。它返回比被调用类高的类的元组类对象，由参数中的值的数量决定。

**语法:**

```
Triplet<String, Integer, Double> triplet = ...
    ...
Quartet<String, Integer, Double, type(s)> quartet = triplet.add(value(s));
```

**参数:**该方法可以将 *n 个值*作为参数，其中:

*   **n** –indicates the number of values based on the *tuple class* (unit, equivalence) to be created as the return object.
*   **Type** –Indicates the type of value passed as a parameter.
*   **Value** -Indicates the value passed as a parameter.

**返回值:**这个方法返回 *TupleClass* 的对象，被调用元组类的组合值和作为参数传递的值。传递的值被添加到被调用的元组类值之后。

下面的程序说明了使用 add()方法的各种方法:

**程序 1:** 当 add()方法用于从 Unit 到 Ennead 的任何类时，以单个值作为参数:

```
// Below is a Java program to demonstrate
// use of add() method with
// single value

import java.util.*;
import org.javatuples.Unit;
import org.javatuples.Pair;

class GfG {
    public static void main(String[] args)
    {
        // Using with() method to instantiate unit object
        Unit<String> unit = Unit.with("Geeks");

        // Using add() to create Pair
        Pair<String, String> pair = unit.add("forGeeks");

        System.out.println(pair);
    }
}
```

**输出:**

```
[Geeks, forGeeks]
```

**程序 2:** 当 add()方法用于从 Unit 到 Ennead 的任何类时，以多个值作为参数:

```
// Below is a Java program to demonstrate
// use of add() method with
// multiple value

import java.util.*;
import org.javatuples.Ennead;
import org.javatuples.Decade;

class GfG {
    public static void main(String[] args)
    {
        // Using with() method to instantiate ennead object
        Ennead<String, String, String, String, String,
               String, String, String, String>
            ennead = Ennead.with("Geeks",
                                 "for",
                                 "Geeks",
                                 "A",
                                 "Computer",
                                 "Science",
                                 "Portal",
                                 "for",
                                 "Geeks");

        // Using add() to create Decade
        Decade<String, String, String, String, String,
               String, String, String, String, String>
            decade = ennead.add("RishabhPrabhu");

        System.out.println(decade);
    }
}
```

**输出:**

```
[Geeks, for, Geeks, A, Computer, Science, Portal, for, Geeks, RishabhPrabhu]
```

**程序 3:** 当 add()方法用于从 Unit 到 Ennead 的任何类，且总值贡献大于 10 时，它显示运行时异常:

```
// Below is a Java program to demonstrate
// use of add() method

import java.util.*;
import org.javatuples.Ennead;
import org.javatuples.Decade;

class GfG {
    public static void main(String[] args)
    {
        // Using with() method to instantiate ennead object
        Ennead<String, String, String, String, String,
               String, String, String, String>
            ennead = Ennead.with("Geeks",
                                 "for",
                                 "Geeks",
                                 "A",
                                 "Computer",
                                 "Science",
                                 "Portal",
                                 "for",
                                 "Geeks");

        // Using add() to create Decade
        Decade<String, String, String, String, String,
               String, String, String, String, String>
            decade = ennead.add("Rishabh", "Prabhu");

        System.out.println(decade);
    }
}
```

**输出:**

```
Exception in thread "main" java.lang.RuntimeException: 
    Uncompilable source code - Erroneous sym type: org.javatuples.Ennead.add
```

注意:同样，它也可以用于任何其他的 JavaTuple 类。