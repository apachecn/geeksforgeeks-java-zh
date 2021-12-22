# Java 中的 chronolocaltdate plus(tempalamount)方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-plustemporalamount-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-plustemporalamount-method-in-java-with-examples/)

**加上**计时日期**界面的**方法，用于返回该计时日期的副本，并添加指定的计时日期。该金额通常为“期间”或“持续时间”，但也可以是实现临时计费界面的任何其他类型。

**语法:**

```
public ChronoLocalDate plus(TemporalAmount amountToAdd)

```

**参数:**此方法只接受一个参数**金额加**即要加的金额，不应该为空。

**返回值:**该方法基于该日期-时间返回**时间地点日期**，并进行加法运算。

下面的程序说明了 plus()方法:

**程序 1:**

```
// Java program to demonstrate
// ChronoLocalDate.plus() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDate object
        ChronoLocalDate zonedlt
            = LocalDate.parse("2018-12-06");

        // add 100 Days to ChronoLocalDate
        ChronoLocalDate value
            = zonedlt.plus(Period.ofDays(100));

        // print result
        System.out.println("ChronoLocalDate after adding Days: "
                           + value);
    }
}
```

**输出:**

```
ChronoLocalDate after adding Days: 2019-03-16

```

**参考文献:**T2