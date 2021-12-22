# Java 中的 ChronoLocalDate 减(long，TemporalUnit)方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-minlong-tempalalunit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-minuslong-temporalunit-method-in-java-with-examples/)

**一个**计时日期**接口的减(长，时间单位)**方法，用于返回该计时日期的一个副本，其中指定数量的单位减去计时日期。如果由于不支持该单位或其他原因而无法减去该金额，则会引发异常。

**语法:**

```java
public ChronoLocalDate minus(long amountToSubtract,
                       TemporalUnit unit)

```

**参数:**此方法接受两个参数:

*   **Amount to Subtract:** is the amount of unit pair result to be subtracted, which may be a negative number.
*   **Unit:** is the amount of unit to be subtracted.

**返回值:**该方法根据该日期时间减去指定的金额返回**时间地点日期**。

**异常:**此方法抛出以下异常:

*   **Abnormal date and time** : If subtraction is not possible,
*   **does not support** : if the company is not supported
*   **Arithmetic exception** : If there is a numerical overflow,

下面的程序说明了减()方法:

**程序 1:**

```java
// Java program to demonstrate
// ChronoLocalDate.minus() method

import java.time.*;
import java.time.temporal.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDate object
        ChronoLocalDate zonedlt
            = LocalDate.parse("2018-12-06");

        // subtract 12 Years to ChronoLocalDate
        ChronoLocalDate value
            = zonedlt.minus(12, ChronoUnit.YEARS);

        // print result
        System.out.println("ChronoLocalDate after "
                           + "subtracting Months: "
                           + value);
    }
}
```

**输出:**

```java
ChronoLocalDate after subtracting Months: 2006-12-06

```

**参考文献:**T2