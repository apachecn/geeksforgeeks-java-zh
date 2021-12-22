# JavaTuples with()方法

> 原文:[https://www.geeksforgeeks.org/java-tuples-with-method/](https://www.geeksforgeeks.org/java-tuples-with-method/)

[org.javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的 **with()** 方法用于以语义优雅的方式实例化元组，值作为参数给出。这个方法可以用于 javatuples 库的任何元组类对象。这个方法是每个 javatuple 类中的静态函数，它返回被调用类的 tuple 类对象，其值由参数中的相应值初始化。

**语法:**

```java
public static <A, B, ..> <em>TupleClass<A, B, ..> with(A a, B b, ..)
```

**参数:**该方法以 *n 值*为参数，其中:

*   **n**–表示基于所使用的*类别*(单位、对等)的数值数量。
*   **A A**–代表 A 中第一个值的类型及其在 A 中的对应值
*   **B b**– represents the type for 2nd value in B and its corresponding value in b.

    **。**
    **。**
    等等。

**返回值:**该方法返回调用该方法的*类*的对象，值作为参数传递。

**异常:**该方法在以下情况下抛出**运行时异常**:

*   当传递的值*与图类中的预期类型不匹配时*
*   当传递的值的数量*小于图类中的预期*时
*   当传递的值的数量*比 TupleClass 中预期的*多时

下面的程序说明了使用()方法的各种方法:

**程序 1:** 当正确使用 with()方法时，此处为 Unit 类:

```java
// Below is a Java program to create
// a Unit tuple from with() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        // Using with() method to instantiate unit object
        Unit<String> unit = Unit.with("GeeksforGeeks");

        System.out.println(unit);
    }
}
```

**输出:**

```java
[GeeksforGeeks]
```

**程序 2:** 当通过的值*与*的预期类型不匹配时:

```java
// Below is a Java program to create
// a Unit tuple from with() method

import java.util.*;
import org.javatuples.Quartet;

class GfG {
    public static void main(String[] args)
    {
        // Using with() method to instantiate unit object
        Quartet<Integer, String, String, Double> quartet
            = Quartet.with(Double.valueOf(1),
                           "GeeksforGeeks",
                           "A computer portal",
                           Double.valueOf(20.18));

        System.out.println(quartet);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.RuntimeException: 
Uncompilable source code - incompatible types: inference variable A has incompatible bounds
    equality constraints: java.lang.Integer
    lower bounds: java.lang.Double
    at MainClass.GfG.main]
```

**程序 3:** 当通过的数值数量*小于预期*时:

```java
// Below is a Java program to create
// a Unit tuple from with() method

import java.util.*;
import org.javatuples.Quartet;

class GfG {
    public static void main(String[] args)
    {
        // Using with() method to instantiate unit object
        Quartet<Integer, String, String, Double> quartet
            = Quartet.with(Integer.valueOf(1),
                           "GeeksforGeeks",
                           "A computer portal");

        System.out.println(quartet);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.RuntimeException: 
Uncompilable source code - Erroneous sym type: org.javatuples.Quartet.with
    at MainClass.GfG.main
```

**程序 4:** 当通过的数值数量*超过预期*时:

```java
// Below is a Java program to create
// a Unit tuple from with() method

import java.util.*;
import org.javatuples.Quartet;

class GfG {
    public static void main(String[] args)
    {
        // Using with() method to instantiate unit object
        Quartet<Integer, String, String, Double> quartet
            = Quartet.with(Integer.valueOf(1),
                           "GeeksforGeeks",
                           "A computer portal",
                           Double.valueOf(20.18),
                           Integer.valueOf(1));

        System.out.println(quartet);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.RuntimeException: 
Uncompilable source code - Erroneous sym type: org.javatuples.Quartet.with
    at MainClass.GfG.main
```

注意:同样，它也可以用于任何其他的 JavaTuple 类。