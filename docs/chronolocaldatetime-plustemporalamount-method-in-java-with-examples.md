# Java 中的 chronolocaldatimeplus(tempalamount)方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-plustemporalamount-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-plustemporalamount-method-in-java-with-examples/)

**计时日期时间**界面的 **plus()** 方法用于返回该计时日期时间的副本，并将指定的数量添加到日期时间中。该金额通常为“期间”或“持续时间”，但也可以是实现临时计费界面的任何其他类型。

**语法:**

```java
default ChronoLocalDateTime plus(TemporalAmount amountToadd)
```

**参数:**此方法只接受一个参数**金额加**即要加的金额，不应该为空。
**返回值:**此方法基于此日期时间返回**计时日期时间**，并进行加法运算，不为空。
**异常:**
该方法抛出以下异常:

*   **日期时间异常**–如果无法添加
*   **算术异常**–如果出现数值溢出

下面的程序说明了加号()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// ChronoLocalDateTime.plus() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ChronoLocalDateTime instance
        ChronoLocalDateTime ldt
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        // Get the String representation of this ChronoLocalDateTime
        System.out.println("Original ChronoLocalDateTime: "
                           + ldt.toString());

        // add 10 Days to ChronoLocalDateTime
        ChronoLocalDateTime value
            = ldt.plus(Period.ofDays(10));

        // print result
        System.out.println("ChronoLocalDateTime after adding Days: "
                           + value);
    }
}
```

**Output:** 

```java
Original ChronoLocalDateTime: 2019-12-31T19:15:30
ChronoLocalDateTime after adding Days: 2020-01-10T19:15:30
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldatetime . html # plus-Java . time .时态. tempalamount-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#plus-java.time.temporal.TemporalAmount-)