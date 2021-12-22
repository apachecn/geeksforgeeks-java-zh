# Java 中的等时区数据时间方法，示例

> 原文:[https://www . geeksforgeeks . org/isochronomics-zoneddatimetemporalacessor-method-in-Java-with-example/](https://www.geeksforgeeks.org/isochronology-zoneddatetimetemporalaccessor-method-in-java-with-example/)

**Java . time . chrono . isochronology 类**的 **zonedDateTime()** 方法用于从另一个 TemporalAccessor 对象获取符合 Iso 日历系统的区域日期和时间。

**语法:**

```java
public ZonedDateTime zonedDateTime(
          TemporalAccessor temporal)

```

**参数:**该方法以任意时态取值器的对象为参数。

**返回值:**该方法从另一个临时进程对象返回根据 Iso 日历系统的区域日期和时间。

以下是说明**区域时间()**方法的示例:

**例 1:**

```java
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
            // LocalDate Object
            LocalDate hidate
                = LocalDate.now();

            // getting IsoChronology
            // used in LocalDate
            IsoChronology crono
                = hidate.getChronology();

            // creating and initializing
            // TemporalAccessor object
            ZonedDateTime zonedate
                = ZonedDateTime
                      .parse(
                          "2018-10-25T23:12:31."
                          + "123+02:00[Europe/Paris]");

            // getting LocalDate and time for the
            // given TemporalAccessor object
            // by using zonedDateTime() method
            ChronoZonedDateTime<LocalDate> date
                = crono.zonedDateTime(zonedate);

            // display the result
            System.out.println(
                "LocalDate and time is: "
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

```java
LocalDate and time is: 2018-10-25T23:12:31.123+02:00[Europe/Paris]

```

**例 2:**

```java
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
            // LocalDate Object
            LocalDate hidate
                = LocalDate.now();

            // getting IsoChronology
            // used in LocalDate
            IsoChronology crono
                = hidate.getChronology();

            // creating and initializing
            // TemporalAccessor object
            LocalDateTime localdate
                = LocalDateTime.parse(
                    "2018-12-30T19:34:50.63");

            // getting LocalDate and time for the
            // given TemporalAccessor object
            // by using zonedDateTime() method
            ChronoZonedDateTime<LocalDate> date
                = crono.zonedDateTime(localdate);

            // display the result
            System.out.println(
                "LocalDate and time is: "
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

```java
passed parameter can not form a date
Exception thrown: java.time.DateTimeException: Unable to obtain ZonedDateTime from TemporalAccessor: 2018-12-30T19:34:50.630 of type java.time.LocalDateTime

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/isochronomics . html # zonedDateTime-Java . time . temporalacessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#zonedDateTime-java.time.temporal.TemporalAccessor-)