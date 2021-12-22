# Java 中的 Instant 减()方法，示例

> 原文:[https://www . geesforgeks . org/instant-减-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-minus-method-in-java-with-examples/)

在 Instant 类中，根据传递给它的参数，有两种类型的减()方法。

### 减(长数量到子管道，临时单位)

**减去()**方法的一个**瞬间**类用来返回这个瞬间的一个副本，减去指定数量的单位。如果由于不支持该单位或其他原因而无法减去该金额，则会引发异常。

**语法:**

```java
public Instant minus(long amountToSubtract,
                     TemporalUnit unit)

```

**参数:**该方法接受两个参数:

*   **amountToSubtract** 是要从结果中减去的单位的数量，可以是负数，并且
*   **单位**是要减去的金额的单位，不为空。

**返回值:**该方法基于该瞬间返回**瞬间**，减去指定的金额。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行减法运算
*   **不支持的 temporaltypexception**–如果不支持该设备
*   **算术异常**–如果出现数值溢出

下面的程序说明了减()方法:

**程序 1:**

```java
// Java program to demonstrate
// Instant.minus() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create an Instant object
        Instant instant
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // subtract 20 DAYS to Instant
        Instant value
            = instant.minus(20, ChronoUnit.DAYS);

        // print result
        System.out.println("Instant after subtracting DAYS: "
                           + value);
    }
}
```

**Output:**

```java
Instant after subtracting DAYS: 2018-12-10T19:34:50.630Z

```

### 减(临时金额到小计)

**减去()**方法的一个**瞬间**类用来返回这个瞬间的副本，指定的数量减去日期时间。该金额通常为“期间”或“持续时间”，但也可以是实现临时计费界面的任何其他类型。

**语法:**

```java
public Instant minus(TemporalAmount amountTosubtract)

```

**参数:**此方法接受一个单参数 **amountTosubtract** 为要减去的量，不应为空。

**返回值:**该方法基于该日期时间进行减法运算，返回**时刻**，不为空。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行减法运算
*   **算术异常**–如果出现数值溢出

下面的程序说明了减()方法:
**程序 1:**

```java
// Java program to demonstrate
// Instant.minus() method

import java.time.*;
public class GFG {
    public static void main(String[] args)
    {

        // create an Instant object
        Instant inst
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // subtract 10 Days to Instant
        Instant value
            = inst.minus(Period.ofDays(10));

        // print result
        System.out.println("Instant after subtracting Days: "
                           + value);
    }
}
```

**Output:**

```java
Instant after subtracting Days: 2018-12-20T19:34:50.630Z

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html #减(java.time .时态. tempalamount)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#minus(java.time.temporal.TemporalAmount))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html #减(long，Java . time . tempalamount)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#minus(long, java.time.temporal.TemporalUnit))