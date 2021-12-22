# Java 中的 Japanese 年表 zonedDateTime(临时访问器)方法，示例

> 原文:[https://www . geeksforgeeks . org/Japanese 年表-zoneddatemetemporalacessor-Java 中的方法-带示例/](https://www.geeksforgeeks.org/japanesechronology-zoneddatetimetemporalaccessor-method-in-java-with-example/)

**Java . time . chrono . Japanese 年表**类的 **zonedDateTime()** 方法用于从另一个 TemporalAccessor 对象获取根据日本日历系统的区域日期和时间。

**语法:**

```
public ZonedDateTime zonedDateTime(
          TemporalAccessor temporal)

```

**参数:**该方法以任意**时态取值器**的对象为参数。

**返回值:**该方法从另一个临时处理器对象返回根据日本日历系统的**区域时间**。

以下是说明**区域时间()**方法的示例:

**例 1:**

```
// Java program to demonstrate
// zonedDateTime() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in JapaneseDate
            JapaneseChronology crono
                = hidate.getChronology();

            // creating and initializing
            // TemporalAccessor object
            ZonedDateTime zonedate
                = ZonedDateTime
                      .parse(
                          "2018-10-25T23:12:31."
                          + "123+02:00[Europe/Paris]");

            // getting JapaneseDate and time for the
            // given TemporalAccessor object
            // by using zonedDateTime() method
            ChronoZonedDateTime<JapaneseDate> date
                = crono.zonedDateTime(zonedate);

            // display the result
            System.out.println(
                "JapaneseDate and time is: "
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
JapaneseDate and time is:
 Japanese Heisei 30-10-25T23:12:31.123+02:00[Europe/Paris]

```

**例 2:**

```
// Java program to demonstrate
// zonedDateTime() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in JapaneseDate
            JapaneseChronology crono
                = hidate.getChronology();

            // creating and initializing
            // TemporalAccessor object
            LocalDateTime localdate
                = LocalDateTime.parse(
                    "2018-12-30T19:34:50.63");

            // getting JapaneseDate and time for the
            // given TemporalAccessor object
            // by using zonedDateTime() method
            ChronoZonedDateTime<JapaneseDate> date
                = crono.zonedDateTime(localdate);

            // display the result
            System.out.println(
                "JapaneseDate and time is: "
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
passed parameter can not form a date
Exception thrown:
 java.time.DateTimeException:
 Unable to obtain ChronoZonedDateTime from TemporalAccessor:
 class java.time.LocalDateTime

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/Japanese yestereo . html # zonedDateTime-Java . time . temporalacessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#zonedDateTime-java.time.temporal.TemporalAccessor-)