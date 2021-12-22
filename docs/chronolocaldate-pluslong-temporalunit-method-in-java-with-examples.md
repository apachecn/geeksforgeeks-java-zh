# Java 中的 ChronoLocalDate plus(long，TemporalUnit)方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-plus long-tempalalunit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-pluslong-temporalunit-method-in-java-with-examples/)

**加上一个**计时日期**接口的(长的，临时的)**方法，用于返回该计时日期的副本，并在计时日期中添加指定数量的单位。如果无法添加金额，因为不支持该单位或其他原因，则会引发异常。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public ChronoLocalDate plus(long amountToAdd,
                      TemporalUnit unit)

```

**参数:**此方法接受两个参数:

*   **Amount toad:** is the unit amount to be added to the result, which may be a negative number.
*   **Unit:** is the amount of the unit to be added.

**返回值:**该方法基于该日期时间返回**时间地点日期**，并添加指定的金额。

下面的程序说明了 plus()方法:

**程序 1:**

```
// Java program to demonstrate
// ChronoLocalDate.plus() method

import java.time.*;
import java.time.temporal.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDate object
        ChronoLocalDate zonedlt
            = LocalDate.parse("2018-12-06");

        // add 300 Months to ChronoLocalDate
        ChronoLocalDate value
            = zonedlt.plus(300, ChronoUnit.MONTHS);

        // print result
        System.out.println("ChronoLocalDate after adding Months : "
                           + value);
    }
}
```

**输出:**

```
ChronoLocalDate after adding Months : 2043-12-06

```

**参考文献:**T2