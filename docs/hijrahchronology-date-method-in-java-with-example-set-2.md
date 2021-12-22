# Java 中的 HijrahChronology date()方法，示例:Set–2

> 原文:[https://www . geesforgeks . org/hijrah 年表-日期-方法-Java-带示例-set-2/](https://www.geeksforgeeks.org/hijrahchronology-date-method-in-java-with-example-set-2/)

**Java . time . chrono . Hijrah 年表**类的 **date()** 方法用于根据 Hijrah 日历系统从另一个临时日历对象获取本地日期。

**语法:**

```
public HijrahDate date(TemporalAccessor temporal)
```

**参数**:该方法以任意时态取值器的**对象为参数。**

**返回值:**该方法从另一个 TemporalAccessor 对象返回根据 Hijrah 日历系统的本地日期。

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
            // creating and initializing  HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology used in HijrahDate
            HijrahChronology crono = hidate.getChronology();

            // creating and initializing TemporalAccessor object
            ZonedDateTime zonedate
                = ZonedDateTime.parse(
                    "2018-10-25T23:12:31."
                    + "123+02:00[Europe/Paris]");

            // getting HijrahDate for the
            // given TemporalAccessor object
            // by using date() method
            HijrahDate date = crono.date(zonedate);

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

**输出:**

```
HijrahDate is: Hijrah-umalqura AH 1440-02-16

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
            // creating and initializing  HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology used in HijrahDate
            HijrahChronology crono = hidate.getChronology();

            // creating and initializing TemporalAccessor object
            LocalDateTime localdate
                = LocalDateTime
                      .parse("2018-12-30T19:34:50.63");

            // getting HijrahDate for the
            // given TemporalAccessor object
            // by using date() method
            HijrahDate date = crono.date(localdate);

            // display the result
            System.out.println("HijrahDate is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
HijrahDate is: Hijrah-umalqura AH 1440-04-23

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/hijrah 年表. html # date-Java . time . chrono . era-int-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#date-java.time.chrono.Era-int-int-int-)