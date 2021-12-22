# Java 中带(TemporalAdjuster)方法的 ChronoZonedDateTime 带示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-with temporalaadjuster-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-withtemporaladjuster-method-in-java-with-examples/)

使用**时区数据时间**界面的**带(时间调整调节器)**方法，使用时间调整调节器调整该日期时间，调整后返回调整后的日期时间的副本。使用指定的调整器策略对象进行调整。计时区域的这个实例是不可变的，不受这个方法调用的影响。简单的调整器用于设置其中一个字段，例如年份字段，在该字段中，更复杂的调整器可能会将时间设置为一年中的最后一天。

**语法:**

```
default ChronoZonedDateTime with(TemporalAdjuster adjuster)

```

**参数:**该方法接受**调节器**作为参数，调节器使用该参数。

**返回值:**该方法根据调整后的时间返回一个时区。

**异常:**此方法抛出以下异常:

*   **Abnormal date and time** -If it cannot be adjusted.
*   **Arithmetic exception** -If there is a numerical overflow.

下面的程序说明了 with()方法:

**程序 1:**

```
// Java program to demonstrate
// ChronoZonedDateTime.with() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoZonedDateTime object
        ChronoZonedDateTime time
            = ZonedDateTime
                  .parse(
                      "1918-10-25T23:12:38.543+02:00[Europe/Paris]");

        // print instance
        System.out.println("ChronoZonedDateTime before"
                           + " adjustment: "
                           + time);

        // apply with method of ChronoZonedDateTime
        ChronoZonedDateTime updatedlocal
            = time.with(Month.OCTOBER)
                  .with(TemporalAdjusters
                            .firstDayOfMonth());

        // print instance
        System.out.println("ChronoZonedDateTime after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

**输出:**

```
ChronoZonedDateTime before adjustment: 1918-10-25T23:12:38.543Z[Europe/Paris]
ChronoZonedDateTime after adjustment: 1918-10-01T23:12:38.543+01:00[Europe/Paris]

```

**程序二:**

```
// Java program to demonstrate
// ChronoZonedDateTime.with() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoZonedDateTime object
        ChronoZonedDateTime time
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // print instance
        System.out.println("ChronoZonedDateTime before"
                           + " adjustment: "
                           + time);

        // apply with method of ChronoZonedDateTime
        ChronoZonedDateTime updatedlocal
            = time.with(Month.JANUARY)
                  .with(TemporalAdjusters
                            .firstDayOfMonth());

        // print instance
        System.out.println("ChronoZonedDateTime after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

**输出:**

```
ChronoZonedDateTime before adjustment: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
ChronoZonedDateTime after adjustment: 2018-01-01T19:21:12.123+05:30[Asia/Calcutta]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronozoneddatetime . html # with-Java . time . temporalaadjuster-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#with-java.time.temporal.TemporalAdjuster-)