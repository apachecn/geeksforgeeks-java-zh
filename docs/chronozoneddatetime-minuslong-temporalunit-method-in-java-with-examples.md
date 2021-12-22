# Java 中的 ChronoZonedDateTime 减(long，TemporalUnit)方法，示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-mins long-tempalalunit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-minuslong-temporalunit-method-in-java-with-examples/)

**减()**方法的一个**时区数据时间**界面用来返回这个日期时间的一个副本，减去指定数量的单位。如果由于不支持该单位或其他原因而无法减去该金额，则会引发异常。

**语法:**

```java
default ChronoZonedDateTime minus(long amountToSubtract,
                           TemporalUnit unit)

```

**参数:**此方法接受两个参数:

*   **Amount to Subtract:** is the amount of unit pair result to be subtracted, which may be a negative number.
*   **Unit:** is the amount of unit to be subtracted.

**返回值:**该方法根据该日期时间，减去指定的金额，返回**时区时间**。

**异常:**此方法抛出以下异常:

*   **Abnormal date and time** : If subtraction is not possible,
*   **does not support** : if the company is not supported.
*   **Arithmetic exception** : If there is a numerical overflow.

下面的程序说明了减()方法:

**程序 1:**

```java
// Java program to demonstrate
// ChronoZonedDateTime.minus() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoZonedDateTime object
        ChronoZonedDateTime zonedlt
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // subtract 30 Months to ChronoZonedDateTime
        ChronoZonedDateTime value
            = zonedlt.minus(30, ChronoUnit.MONTHS);

        // print result
        System.out.println("ChronoZonedDateTime after"
                           + " subtracting Months:\n "
                           + value);
    }
}
```

**输出:**

```java
ChronoZonedDateTime after subtracting Months:
 2016-06-06T19:21:12.123+05:30[Asia/Calcutta]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronozoneddatetime . html #减-long-Java . time . temporalunit-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#minus-long-java.time.temporal.TemporalUnit-)