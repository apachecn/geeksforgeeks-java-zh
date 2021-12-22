# Java 中的 time zoneddatetime plus(tempalamount)方法，示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-plustemporalamount-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-plustemporalamount-method-in-java-with-examples/)

**plus()** 方法的一个**时空数据时间**类用来返回这个日期时间的一个副本，指定的数量加到日期时间。该金额通常为“期间”或“持续时间”，但也可以是实现临时计费界面的任何其他类型。

**语法:**

```
public ChronoZonedDateTime plus(TemporalAmount amountToadd)
```

**参数:**此方法只接受一个参数**金额加**即要加的金额，不应该为空。

**返回值:**该方法基于该日期时间返回**时区时间**，并进行加法运算，不为空

**异常:**该方法抛出以下异常:

*   **日期时间异常**:如果无法添加
*   **算术异常**:如果出现数值溢出

下面的程序说明了 plus()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// ChronoZonedDateTime.plus() method

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

        // add 10 Days to ChronoZonedDateTime
        ChronoZonedDateTime value
            = zonedlt.plus(Period.ofDays(10));

        // print result
        System.out.println("ChronoZonedDateTime after"
                           + " adding Days:\n "
                           + value);
    }
}
```

**Output:** 

```
ChronoZonedDateTime after adding Days:
 2018-12-16T19:21:12.123+05:30[Asia/Calcutta]
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronozoneddatetime . html # plus-Java . time . temporalamont-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#plus-java.time.temporal.TemporalAmount-)T4】