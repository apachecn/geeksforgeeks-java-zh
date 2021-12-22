# Java 中的 ChronoLocalDate 减(TemporalAmount)方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-mintimealamount-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-minustemporalamount-method-in-java-with-examples/)

**一个**计时本地日期**接口的减(临时计数)**方法，用于返回该计时本地日期的副本，其中指定的数量减去计时本地日期。该金额通常为“期间”或“持续时间”，但也可以是实现临时计费界面的任何其他类型。

**语法:**

```java
public ChronoLocalDate minus(TemporalAmount amountTosubtract)

```

**参数:**此方法接受一个单参数 **amountTosubtract** 为要减去的量，不应为空。

**返回值:**该方法基于该日期时间进行减法运算，返回**时间位置日期**，不为空。

**异常:**此方法抛出以下异常:

*   **Abnormal date and time:** If subtraction is not possible,
*   **Arithmetic exception:** If there is a numerical overflow

下面的程序说明了减()方法:

**程序 1:**

```java
// Java program to demonstrate
// ChronoLocalDate.minus() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDate object
        ChronoLocalDate zonedlt
            = LocalDate.parse("2018-12-06");

        // subtract 30 Days to ChronoLocalDate
        ChronoLocalDate value
            = zonedlt.minus(Period.ofDays(30));

        // print result
        System.out.println("ChronoLocalDate after"
                           + " subtracting Days: "
                           + value);
    }
}
```

**输出:**

```java
ChronoLocalDate after subtracting Days: 2018-11-06

```

**参考文献:**T2