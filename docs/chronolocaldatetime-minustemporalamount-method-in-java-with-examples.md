# Java 中的 ChronoLocalDateTime 减(TemporalAmount)方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-minostalamount-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-minustemporalamount-method-in-java-with-examples/)

**计时日期时间**接口的**减()**方法用于返回该计时日期时间的副本，其中指定的数量减去日期时间。该金额通常为“期间”或“持续时间”，但也可以是实现临时计费界面的任何其他类型。

**语法:**

```java
default ChronoLocalDateTime minus(TemporalAmount amountTosubtract)

```

**参数:**此方法接受一个单参数 **amountTosubtract** 为要减去的量，不应为空。

**返回值:**该方法基于该日期时间进行减法运算，返回**时间位置日期时间**，不为空。

**异常:**
此方法抛出以下异常:

*   **日期时间异常**–如果无法进行减法运算
*   **算术异常**–如果出现数值溢出

下面的程序说明了减()方法:
**程序 1:**

```java
// Java program to demonstrate
// ChronoLocalDateTime.minus() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ChronoLocalDateTime instance
        ChronoLocalDateTime ldt
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        // Get the String representation
        // of this ChronoLocalDateTime
        System.out.println("Original ChronoLocalDateTime: "
                           + ldt.toString());

        // subtract 10 Days to ChronoLocalDateTime
        ChronoLocalDateTime value
            = ldt.minus(Period.ofDays(10));

        // print result
        System.out.println("ChronoLocalDateTime after"
                           + " subtracting Days: "
                           + value);
    }
}
```

**Output:**

```java
Original ChronoLocalDateTime: 2019-12-31T19:15:30
ChronoLocalDateTime after subtracting Days: 2019-12-21T19:15:30

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldatetime . html #减-java.time .时态. tempalamount-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#minus-java.time.temporal.TemporalAmount-)