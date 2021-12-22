# Java 中的等时区数据时间(Instant，ZoneId)方法，示例

> 原文:[https://www . geesforgeks . org/isochronomics-zoneddatetimeinstant-zoneid-method-in-Java-with-example/](https://www.geeksforgeeks.org/isochronology-zoneddatetimeinstant-zoneid-method-in-java-with-example/)

**Java . time . chrono . isochronology**类的 **zonedDateTime()** 方法用于根据特定时刻的 Iso 日历检索特定区域的日期和时间。

**语法:**

```java
public ZonedDateTime zonedDateTime(Instant instant,
                                   ZoneId zone)
```

**参数:**该方法以下列参数为参数。

*   **Instantaneous:** is instantaneous.
*   Type of object **area:** is zoneId.

类型的对象

**返回值:**该方法根据特定时刻的 Iso 日历返回特定区域的日期和时间。

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
            // creating and initializing LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology used in LocalDate
            IsoChronology crono = hidate.getChronology();

            // getting LocalDate and time for the
            // given Instant and ZoneId
            // by using zonedDateTime() method
            ChronoZonedDateTime<LocalDate> date
                = crono.zonedDateTime(
                    Instant.now(),
                    ZoneId.systemDefault());

            // display the result
            System.out.println("LocalDate and time is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can "
                               + "not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
LocalDate and time is: 2020-03-10T02:37:13.036Z[Etc/UTC]

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
            // creating and initializing LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology used in LocalDate
            IsoChronology crono = hidate.getChronology();

            // getting HijrahDate and time for the
            // given Instant and ZoneId
            // by using zonedDateTime() method
            ChronoZonedDateTime<LocalDate> date
                = crono.zonedDateTime(
                    Instant.ofEpochSecond(25000),
                    ZoneId.systemDefault());

            // display the result
            System.out.println("LocalDate and time is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can "
                               + "not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
LocalDate and time is: 1970-01-01T06:56:40Z[Etc/UTC]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/isochronomics . html # zonedDateTime-Java . time . instant-Java . time . zoneid-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#zonedDateTime-java.time.Instant-java.time.ZoneId-)