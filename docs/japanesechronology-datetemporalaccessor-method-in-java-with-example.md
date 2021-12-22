# Java 中的日本纪年日期(临时处理器)方法，示例

> 原文:[https://www . geeksforgeeks . org/Japanese 年表-datetime alaccessor-method-in-Java-with-example/](https://www.geeksforgeeks.org/japanesechronology-datetemporalaccessor-method-in-java-with-example/)

**Java . time . chrono . Japanese 年表**类的 **date()** 方法用于从另一个 TemporalAccessor 对象获取根据日本日历系统的日本日期。

**语法:**

```
public JapaneseDate date(TemporalAccessor temporal)
```

**参数**:该方法以任意时态取值器的**对象为参数。**

**返回值:**该方法从另一个 TemporalAccessor 对象返回根据日本日历系统的本地日期。

以下是说明**日期()**方法的示例:

**例 1:**

```
// Java program to demonstrate
// date() method

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
            JapaneseDate hidate = JapaneseDate.now();

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
            // by using date() method
            JapaneseDate date = crono.date(zonedate);

            // display the result
            System.out.println("JapaneseDate is: " + date);
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
JapaneseDate is: Japanese Heisei 30-10-25

```

**例 2:**

```
// Java program to demonstrate
// date() method

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
            // by using date() method
            JapaneseDate date = crono.date(localdate);

            // display the result
            System.out.println("JapaneseDate is: " + date);
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
JapaneseDate is: Japanese Heisei 30-12-30

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/Japanese seriogram . html # date-Java . time . temporal . temporal accessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#date-java.time.temporal.TemporalAccessor-)