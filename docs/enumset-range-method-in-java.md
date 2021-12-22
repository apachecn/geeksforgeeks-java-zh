# Java 中的枚举范围()方法

> 原文:[https://www.geeksforgeeks.org/enumset-range-method-in-java/](https://www.geeksforgeeks.org/enumset-range-method-in-java/)

java 中的 Java . util . enumset . range(*E start _ point，E end_point* )方法用于创建一个枚举集，其中的元素由参数中指定的范围定义。

**语法:**

```
Enum_set = EnumSet.range(*E start_point, E end_point*)
```

**参数:**该方法接受枚举的对象类型的两个参数:

*   *start_point:* 这是指需要添加到枚举集中的起始元素。
*   *end_point:* 这是指需要添加到枚举集中的最后一个元素。

**返回值:**方法返回指定范围内提到的元素创建的枚举集。

**异常:**该方法抛出两种类型的异常:

*   *如果任何开始或最后一个元素为空，将引发 NullPointRexception*。
*   *当第一个元素相对于位置大于最后一个元素时，抛出 IllegalArgumentException* 。

下面的程序说明了 range()方法的使用:
**程序 1:**

```
// Java program to demonstrate range() method
import java.util.*;

// Creating an enum of GFG type
enum GFG {
    Welcome,
    To,
    The,
    World,
    of,
    Geeks
}
;

public class Enum_Set_Demo {

    public static void main(String[] args)
    {

        // Creating an EnumSet
        EnumSet<GFG> e_set;

        // Input the values using range()
        e_set = EnumSet.range(GFG.The, GFG.Geeks);

        // Displaying the new set
        System.out.println("The enum set is: " + e_set);
    }
}
```

**Output:**

```
The enum set is: [The, World, of, Geeks]

```

**程序 2:**

```
// Java program to demonstrate range() method
import java.util.*;

// Creating an enum of CARS type
enum CARS {
    RANGE_ROVER,
    MUSTANG,
    CAMARO,
    AUDI,
    BMW
}
;

public class Enum_Set_Demo {

    public static void main(String[] args)
    {

        // Creating an EnumSet
        EnumSet<CARS> e_set;

        // Input the values using range()
        e_set = EnumSet.range(CARS.RANGE_ROVER, CARS.CAMARO);

        // Displaying the new set
        System.out.println("The enum set is: " + e_set);
    }
}
```

**Output:**

```
The enum set is: [RANGE_ROVER, MUSTANG, CAMARO]

```