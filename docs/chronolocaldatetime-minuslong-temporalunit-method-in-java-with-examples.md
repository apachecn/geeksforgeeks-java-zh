# Java 中的 ChronoLocalDateTime 减(长，TemporalUnit)方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-minlong-tempalalunit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-minuslong-temporalunit-method-in-java-with-examples/)

**计时本地日期时间**接口的**减()**方法用于返回该计时本地日期时间的副本，并减去指定数量的单位。如果由于不支持该单位或其他原因而无法减去该金额，则会引发异常。

**语法:**

```java
default ChronoLocalDateTime<D> minus(long amountToSubtract, 
                                 TemporalUnit unit)

```

**参数:**该方法接受两个参数 **amountToSubtract** 可以为负数，也可以接受**单位**为要减去的量的单位，不为空。

**返回值:**该方法根据该时间位置日期时间返回**时间位置日期时间**，减去指定的金额。

**异常:**此方法抛出以下异常:

*   **Abnormal date and time** -If subtraction is not possible
*   **[Arithmetic exception](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/)** -If there is a numerical overflow,

下面的程序说明了减()方法:

**程序 1:**

```java
// Java program to demonstrate
// ChronoLocalDateTime.minus() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

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

        // subtract 200 DAYS to ChronoLocalDateTime
        ChronoLocalDateTime value
            = ldt.minus(200, ChronoUnit.DAYS);

        // print result
        System.out.println("ChronoLocalDateTime after"
                           + " subtracting DAYS: "
                           + value);
    }
}
```

**输出:**

```java
Original ChronoLocalDateTime: 2019-12-31T19:15:30
ChronoLocalDateTime after subtracting DAYS: 2019-06-14T19:15:30

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldatetime . html #减-long-Java . time . temporalunit-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#minus-long-java.time.temporal.TemporalUnit-)