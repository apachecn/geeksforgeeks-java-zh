# JavaTuples removeFromX()方法

> 原文:[https://www . geesforgeks . org/Java-元组-removefromx-method/](https://www.geeksforgeeks.org/java-tuples-removefromx-method/)

[org.javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的 **removeFromX()** 方法用于从索引 x 中移除现有元组中的值。由于 javatuples 是不可变的，因此从现有元组中移除值会导致新元组少一个值。例如，从对元组中移除一个值会导致形成一个单位元组。此方法可用于 javatuples 库的任何元组类对象，但 Unit 类除外，因为 Unit 是 JavaTuples 库中可用的最小类，只有 1 个值。它返回比被调用类小的类的元组类对象。

**语法:**

```
Quartet<String, Integer, Double, String> quartet = ...
    ...
Triplet<String, Integer, Double> triplet = quartet.removeFromX();
```

这里 **X** 代表要从中删除值的索引。

**返回值:**该方法返回比被调用类小的类的元组类对象。移除的值来自方法名中提到的索引 X。

**注意:**此方法不存在单位类、键值类和标签值类。

下面的程序说明了使用 removeFromX()方法的各种方法:

**程序 1:** 当 removeFromX()方法用于从 Pair 到 Decade 的任何类时，直接值作为参数:

```
// Below is a Java program to demonstrate
// use of removeFromX() method

import java.util.*;
import org.javatuples.Unit;
import org.javatuples.Pair;

class GfG {
    public static void main(String[] args)
    {
        // Creating a Pair with 2 values
        Pair<String, String> pair = Pair.with("GeeksforGeeks",
                                              "A computer science portal");

        // Using with() method to instantiate unit object
        Unit<String> unit = pair.removeFrom1();

        // Printing the returned Unit
        System.out.println(unit);
    }
}
```

**输出:**

```
[GeeksforGeeks]
```

**节目 2:**

```
// Below is a Java program to demonstrate
// use of removeFromX() method

import java.util.*;
import org.javatuples.Ennead;
import org.javatuples.Decade;

class GfG {
    public static void main(String[] args)
    {
        // Using with() method to instantiate Decade object
        Decade<Integer, Integer, Integer,
               Integer, Integer, Integer,
               Integer, Integer, Integer,
               Integer>
            decade
            = Decade.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6),
                          Integer.valueOf(7),
                          Integer.valueOf(8),
                          Integer.valueOf(9),
                          Integer.valueOf(10));

        // Using removeFromX() to create Ennead
        Ennead<Integer, Integer, Integer,
               Integer, Integer, Integer,
               Integer, Integer, Integer>
            ennead
            = decade.removeFrom0();

        // Printing the formed Ennead
        System.out.println(ennead);
    }
}
```

**输出:**

```
[2, 3, 4, 5, 6, 7, 8, 9, 10]
```

**注:**同样可以和其他 JavaTuple 类一起使用。