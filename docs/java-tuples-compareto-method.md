# JavaTuples compareTo()方法

> 原文:[https://www.geeksforgeeks.org/java-tuples-compareto-method/](https://www.geeksforgeeks.org/java-tuples-compareto-method/)

[org.javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的 **compareTo()** 方法用于比较 Tuple 对象的顺序和作为参数传递的对象。这个方法可以用于 javatuples 库的任何元组类对象。它从被调用的对象返回传递的对象中第一个不同元素的 ASCII 值的差值。

**语法:**

```java
tupleObject1.compareTo(tupleObject2)
```

**参数:**该方法取一个强制参数 *tupleObject2* ，即要比较的 JavaTuple 对象。

**返回值:**该方法计算传递对象中第一个不同元素的 ascii 值与被调用对象的不同。它可能是负值、0 或正整数值。

下面的程序说明了使用 compareTo()方法的各种方法:

**程序 1:** 当比较()给出否定结果时:

```java
// Below is a Java program to demonstrate
// use of compareTo() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        // Using with() method to instantiate unit object
        Unit<String> unit1 = Unit.with("a");

        // Using with() method to instantiate unit object
        Unit<String> unit2 = Unit.with("z");

        // Using compareTo()
        int result = unit1.compareTo(unit2);

        System.out.println(unit1.compareTo(unit2));
    }
}
```

**输出:**

```java
-25
```

**说明:**
a 的 ascii 值为 97，z 的 ascii 值为 122。因此，a.compareTo(z)的结果是-25 (=122-97)。

**程序 1:** 当比较()给出 0 作为结果时:

```java
// Below is a Java program to demonstrate
// use of compareTo() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        // Using with() method to instantiate unit object
        Unit<String> unit1 = Unit.with("Geeks");

        // Using with() method to instantiate unit object
        Unit<String> unit2 = Unit.with("Geeks");

        // Using compareTo()
        int result = unit1.compareTo(unit2);

        System.out.println(unit1.compareTo(unit2));
    }
}
```

**输出:**

```java
0
```

**说明:**
既然“极客”和“极客”一样。因此他们是平等的。所以在这种情况下，极客比较得到了 0。

**程序 3:** 当 compareTo()给出正结果时:

```java
// Below is a Java program to demonstrate
// use of compareTo() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        // Using with() method to instantiate unit object
        Unit<String> unit1 = Unit.with("z");

        // Using with() method to instantiate unit object
        Unit<String> unit2 = Unit.with("A");

        // Using compareTo()
        int result = unit1.compareTo(unit2);

        System.out.println(unit1.compareTo(unit2));
    }
}
```

**输出:**

```java
57
```

**说明:**
A 的 ascii 值是 65，z 的 ascii 值是 122。因此，z.compareTo(A)的结果是 57 (=122-65)。

注意:同样，它也可以用于任何其他的 JavaTuple 类。