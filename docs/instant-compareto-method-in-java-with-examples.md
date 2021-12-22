# Java 中的 Instant compareTo()方法与示例

> 原文:[https://www . geeksforgeeks . org/instant-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-compareto-method-in-java-with-examples/)

**Instant 类**的**compare to(Instant other Instant)**方法用于将此实例与作为参数传递的实例进行比较，以检查两个实例是否相等。两个实例之间的比较是基于时刻的时间线位置。此方法返回的值确定如下:

*   If this instance is larger than the instance passed as a parameter, a positive value is returned.
*   Returns zero (0) if this instance is equal to the instance passed as a parameter.
*   If this instance is smaller than the instance passed as a parameter, a negative value is returned.

**语法:**

```
public int compareTo(Instant otherInstant)
```

**参数:**该方法接受一个强制参数 **otherInstant** ，即需要比较的另一个时刻，不应该为空。

**返回值:**该方法返回一个整数值，如下所示:

*   如果此实例大于作为参数传递的实例，则返回正值
*   如果此实例等于作为参数传递的实例，则返回零(0)
*   如果此实例小于作为参数传递的实例，则返回负值。

**异常:**如果作为参数传递的 otherInstant 为空，该方法抛出 **NullPointerException** 。

下面的程序说明了 Instant.compareTo()方法:

**程序 1:** 当该实例大于

```
// Java program to demonstrate
// Instant.compareTo() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create two instance objects
        Instant instant1
            = Instant.parse("2018-10-20T16:55:30.00Z");

        Instant instant2
            = Instant.parse("2017-10-20T16:55:30.00Z");

        // print Instant Values
        System.out.println("Instant1: "
                           + instant1);
        System.out.println("Instant2: "
                           + instant2);

        // compare both instant
        int value = instant1.compareTo(instant2);

        if (value > 0)
            System.out.println("Instant1 is greater");
        else if (value == 0)
            System.out.println("Instant1 is equal to Instant2");
        else
            System.out.println("Instant2 is greater");
    }
}
```

**时输出:**

```
Instant1: 2018-10-20T16:55:30Z
Instant2: 2017-10-20T16:55:30Z
Instant1 is greater

```

**程序 2:** 当作为参数传递的其他瞬间大于

```
// Java program to demonstrate
// Instant.compareTo() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create two instance objects
        Instant instant1
            = Instant.parse("2017-10-20T16:55:30.00Z");

        Instant instant2
            = Instant.parse("2018-10-20T16:55:30.00Z");

        // print Instant Values
        System.out.println("Instant1: "
                           + instant1);
        System.out.println("Instant2: "
                           + instant2);

        // compare both instant
        int value = instant1.compareTo(instant2);

        if (value > 0)
            System.out.println("Instant1 is greater");
        else if (value == 0)
            System.out.println("Instant1 is equal to Instant2");
        else
            System.out.println("Instant2 is greater");
    }
}
```

**输出:**

```
Instant1: 2017-10-20T16:55:30Z
Instant2: 2018-10-20T16:55:30Z
Instant2 is greater

```

**程序 1:** 当两个实例相等时

```
// Java program to demonstrate
// Instant.compareTo() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create two instance objects
        Instant instant1
            = Instant.parse("2018-10-20T16:55:30.00Z");

        Instant instant2
            = Instant.parse("2018-10-20T16:55:30.00Z");

        // print Instant Values
        System.out.println("Instant1: "
                           + instant1);
        System.out.println("Instant2: "
                           + instant2);

        // compare both instant
        int value = instant1.compareTo(instant2);

        if (value > 0)
            System.out.println("Instant1 is greater");
        else if (value == 0)
            System.out.println("Instant1 is equal to Instant2");
        else
            System.out.println("Instant2 is greater");
    }
}
```

**输出:**

```
Instant1: 2018-10-20T16:55:30Z
Instant2: 2018-10-20T16:55:30Z
Instant1 is equal to Instant2

```

**程序 4:** 显示空指针异常

```
// Java program to demonstrate
// Instant.compareTo() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create two instance objects
        Instant instant1
            = Instant.parse("2018-10-20T16:55:30.00Z");

        Instant instant2 = null;

        try {

            // compare both instant
            int value = instant1.compareTo(instant2);
        }
        catch (NullPointerException e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```
Exception: java.lang.NullPointerException

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # compare to(Java . time . instant)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#compareTo(java.time.Instant))