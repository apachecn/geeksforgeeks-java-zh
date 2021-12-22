# JavaTuples setAtX()方法

> 原文:[https://www.geeksforgeeks.org/java-tuples-setatx-method/](https://www.geeksforgeeks.org/java-tuples-setatx-method/)

[org.javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的 **setAtX()** 方法用于在索引 x 处更改现有元组中的值。由于 javatuples 是不可变的，因此更改现有元组中的值会导致在索引 x 处具有修改后的值的新元组。它返回在索引 x 处具有更改后的值的被调用类的元组类对象

**语法:**

```java
Quartet<String, Integer, Double, String> quartet = ...
    ...
Quartet otherQuartet = quartet.setAtX(value);
```

这里 **X** 代表要改变数值的指数。

**返回值:**该方法返回被调用类的元组类对象，索引 x 处的值发生了变化

**注意:**此方法不存在键值类和标签值类。

下面的程序说明了使用 setAtX()方法的各种方法:

**程序 1:** 当 setAtX()方法用于从单位到十进制的任何类时，直接值作为参数:

```java
// Below is a Java program to demonstrate
// use of setAtX() method

import java.util.*;
import org.javatuples.Pair;

class GfG {
    public static void main(String[] args)
    {
        // Creating a Pair with 2 values
        Pair<String, String> pair = Pair.with("GeeksforGeeks",
                                              "A computer science portal");

        // Using Pair() method to instantiate unit object
        Pair otherPair = pair.setAt1("by Sandeep Jain");

        // Printing the returned Pair
        System.out.println(otherPair);
    }
}
```

**输出:**

```java
[GeeksforGeeks, by Sandeep Jain]
```

**节目 2:**

```java
// Below is a Java program to demonstrate
// use of setAtX() method

import java.util.*;
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

        // Using setAtX()
        Decade otherDecade = decade.setAt9(100);

        // Printing the formed Decade
        System.out.println(otherDecade);
    }
}
```

**输出:**

```java
[1, 2, 3, 4, 5, 6, 7, 8, 9, 100]
```

**注:**同样可以和其他 JavaTuple 类一起使用。