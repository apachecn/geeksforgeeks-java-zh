# Java 中的 HijrahChronology localDateTime()方法，示例:Set–2

> 原文:[https://www . geesforgeks . org/hijrah 年表-local datetime-Java 中的方法-带示例-set-2/](https://www.geeksforgeeks.org/hijrahchronology-localdatetime-method-in-java-with-example-set-2/)

类的 **localDateTime()** 方法用于根据 Hijrah 日历系统从时态访问器的任何其他对象中检索本地日期和时间。

**语法:**

```
public ChronoLocalDateTime localDateTime(TemporalAccessor temporal)
```

**参数**:该方法以任意时态取值器的**对象为参数。**

**返回值:**该方法根据回历系统从时态访问器的任何其他对象返回**本地日期**和时间。

以下是说明 **localDateTime()** 方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

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
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.now();

            // getting HijrahChronology
            // used in HijrahDate
            HijrahChronology crono
                = hidate.getChronology();

            // creating and initializing
            // TemporalAccessor object
            ZonedDateTime zonedate
                = ZonedDateTime.parse(
                    "2018-10-25T23:12:31."
                    + "123+02:00[Europe/Paris]");

            // getting HijrahDate for the
            // given TemporalAccessor object
            // by using localDateTime() method
            ChronoLocalDateTime<HijrahDate> date
                = crono.localDateTime(zonedate);

            // display the result
            System.out.println("HijrahDate is: "
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

**Output:** 

```
HijrahDate is: Hijrah-umalqura AH 1440-02-16T23:12:31.123
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

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
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology
            // used in HijrahDate
            HijrahChronology crono
                = hidate.getChronology();

            // creating and initializing
            // TemporalAccessor object
            LocalDateTime localdate
                = LocalDateTime
                      .parse("2018-12-30T19:34:50.63");

            // getting HijrahDate for the
            // given TemporalAccessor object
            // by using localDateTime() method
            ChronoLocalDateTime<HijrahDate> date
                = crono.localDateTime(localdate);

            // display the result
            System.out.println("HijrahDate is: " + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:** 

```
HijrahDate is: Hijrah-umalqura AH 1440-04-23T19:34:50.630
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/hijrah 年表. html # local datetime-Java . time . temporalacessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#localDateTime-java.time.temporal.TemporalAccessor-)T4】