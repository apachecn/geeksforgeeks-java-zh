# Java 中的日语年表 localDateTime()方法，示例

> 原文:[https://www . geeksforgeeks . org/Japanese 年表-local datetime-Java 中的方法-示例/](https://www.geeksforgeeks.org/japanesechronology-localdatetime-method-in-java-with-example/)

类的 **localDateTime()** 方法用于根据日语日历系统从时态访问器的任何其他对象中检索本地日期和时间。

**语法:**

```
public ChronoLocalDateTime localDateTime
               (TemporalAccessor temporal)

```

**参数**:该方法以任意时态取值器的**对象为参数。**

**返回值:**此方法从时态访问器的任何其他对象返回**本地日期**和根据日本日历系统的时间。

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
                = ZonedDateTime.parse(
                    "2018-10-25T23:12:31."
                    + "123+02:00[Europe/Paris]");

            // getting JapaneseDate for the
            // given TemporalAccessor object
            // by using localDateTime() method
            ChronoLocalDateTime<JapaneseDate> date
                = crono.localDateTime(zonedate);

            // display the result
            System.out.println("JapaneseDate is: "
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
JapaneseDate is: Japanese Heisei 30-10-25T23:12:31.123

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
                = LocalDateTime
                      .parse("2018-12-30T19:34:50.63");

            // getting JapaneseDate for the
            // given TemporalAccessor object
            // by using localDateTime() method
            ChronoLocalDateTime<JapaneseDate> date
                = crono.localDateTime(localdate);

            // display the result
            System.out.println("JapaneseDate is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
JapaneseDate is: Japanese Heisei 30-12-30T19:34:50.630

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/Japanese seriogram . html # local datetime-Java . time . temporal . temporal accessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#localDateTime-java.time.temporal.TemporalAccessor-)