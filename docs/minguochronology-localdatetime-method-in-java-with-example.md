# Java 中的 minuo 年表 localDateTime()方法，示例

> 原文:[https://www . geeksforgeeks . org/minguoberogram-local datetime-Java 中的方法-带示例/](https://www.geeksforgeeks.org/minguochronology-localdatetime-method-in-java-with-example/)

类的 **localDateTime()** 方法用于根据民国日历系统从时态访问器的任何其他对象中检索本地日期和时间。

**语法:**

```
public ChronoLocalDateTime 
    localDateTime(TemporalAccessor temporal)

```

**参数**:该方法以任意时态取值器的**对象为参数。**

**返回值:**该方法从时态访问器的任何其他对象返回**本地日期**和根据民国日历系统的时间。

以下是说明 **localDateTime()** 方法的示例:

**例 1:**

```
// Java program to demonstrate
// localDateTime() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now();

            // getting MinguoChronology
            // used in MinguoDate
            MinguoChronology crono
                = hidate.getChronology();

            // creating and initializing
            // TemporalAccessor object
            ZonedDateTime zonedate
                = ZonedDateTime.parse(
                    "2018-10-25T23:12:31."
                    + "123+02:00[Europe/Paris]");

            // getting MinguoDate for the
            // given TemporalAccessor object
            // by using localDateTime() method
            ChronoLocalDateTime<MinguoDate> date
                = crono.localDateTime(zonedate);

            // display the result
            System.out.println("MinguoDate is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
MinguoDate is: Minguo ROC 107-10-25T23:12:31.123

```

**例 2:**

```
// Java program to demonstrate
// localDateTime() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now();

            // getting MinguoChronology
            // used in MinguoDate
            MinguoChronology crono
                = hidate.getChronology();

            // creating and initializing
            // TemporalAccessor object
            LocalDateTime localdate
                = LocalDateTime
                      .parse("2018-12-30T19:34:50.63");

            // getting MinguoDate for the
            // given TemporalAccessor object
            // by using localDateTime() method
            ChronoLocalDateTime<MinguoDate> date
                = crono.localDateTime(localdate);

            // display the result
            System.out.println("MinguoDate is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
MinguoDate is: Minguo ROC 107-12-30T19:34:50.630

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/minguoserterog . html # local datetime-Java . time .时态. temporalacessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#localDateTime-java.time.temporal.TemporalAccessor-)