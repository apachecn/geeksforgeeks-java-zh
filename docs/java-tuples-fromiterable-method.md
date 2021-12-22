# JavaTuples fromIterable()方法

> 原文:[https://www . geesforgeks . org/Java-元组-fromiterable-method/](https://www.geeksforgeeks.org/java-tuples-fromiterable-method/)

[org.javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的 **fromIterable()** 方法用于以语义优雅的方式实例化元组，可迭代的值作为参数给出。这个方法可以用于 javatuples 库的任何元组类对象。它是每个 javatuple 类中的一个静态函数，它返回被调用类的 tuple 类对象，其值由 iterable 的相应值初始化。

**方法申报:**

```java
public static <X> TupleClass<X> fromIterable(Iterable<X> iterable)
```

**语法:**

```java
TupleClass<X> obj = TupleClass.fromIterable(Iterable<X> iterable)
```

**参数:**该方法以*可迭代*为参数，其中:

*   **X**–表示可迭代表中值的数据类型。
*   **可迭代**–表示要插入到 TupleClass 中的值的可迭代。
*   **类类**–代表像单位、五重奏、十年等使用的 JavaTuple 类。

**返回值:**该方法返回*类*的对象，该对象调用方法，可迭代的值作为参数传递。

下面的程序说明了使用 fromIterable()方法的各种方法:

**程序 1:** 使用 fromIterable()和单元类:

```java
// Below is a Java program to create
// a Unit tuple from fromIterable() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        // Creating an iterable with one value
        Iterable<String> itr = Arrays.asList("GeeksforGeeks");

        // Using fromIterable() method
        Unit<String> unit = Unit.fromIterable(itr);

        System.out.println(unit);
    }
}
```

**输出:**

```java
[GeeksforGeeks]
```

**程序 2:** 使用 fromIterable()配合十进制类:

```java
// Below is a Java program to create
// a Unit tuple from fromIterable() method

import java.util.*;
import org.javatuples.Decade;

class GfG {
    public static void main(String[] args)
    {
        // Creating an iterable with 10 value
        Iterable<String> itr = Arrays.asList("GeeksforGeeks",
                                             "Geeks",
                                             "for",
                                             "Geeks",
                                             "A",
                                             "Computer",
                                             "Science",
                                             "Portal",
                                             "for",
                                             "Geeks",
                                             "RishabhPrabhu");

        // Using fromIterable() method
        Decade<String, String, String, String, String,
               String, String, String, String, String>
            decade = Decade.fromIterable(itr);

        System.out.println(decade);
    }
}
```

**输出:**

```java
[Geeks, for, Geeks, A, Computer, Science, Portal, for, Geeks, RishabhPrabhu]
```

**注意:**同样，它也可以用于任何其他 JavaTuple 类。