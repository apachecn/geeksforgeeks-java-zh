# Java 中的 ChronoZonedDateTime 减(TemporalAmount)方法，示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-mintimealamount-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-minustemporalamount-method-in-java-with-examples/)

**减()**方法的一个**时空数据**类用来返回这个日期时间的一个副本，其中指定的数量减去日期时间。该金额通常为“期间”或“持续时间”，但也可以是实现临时计费界面的任何其他类型。

**语法:**

```java
default ChronoZonedDateTime minus(TemporalAmount amountTosubtract)

```

**参数:**此方法接受一个单参数 **amountTosubtract** 为要减去的量，不应为空。

**返回值:**该方法基于该日期时间进行减法运算，返回**时区时间**，不为空

**异常:**此方法抛出以下异常:

*   **Abnormal date and time** : If subtraction is not possible </li
*   **Arithmetic exception** : If there is a numerical overflow,

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

        // subtract 10 Days to ChronoZonedDateTime
        ChronoZonedDateTime value
            = zonedlt.minus(Period.ofDays(10));

        // print result
        System.out.println("ChronoZonedDateTime after"
                           + " subtracting Days:\n "
                           + value);
    }
}
```

**输出:**

```java
ChronoZonedDateTime after subtracting Days:
 2018-11-26T19:21:12.123+05:30[Asia/Calcutta]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronozoneddatetime . html #减-Java . time . temporal mount-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#minus-java.time.temporal.TemporalAmount-)