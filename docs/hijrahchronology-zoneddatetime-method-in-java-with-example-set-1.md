# Java 中的 hijrah 年表 zonedDateTime()方法，示例:设置 1

> 原文:[https://www . geesforgeks . org/hijrah 年表-zoneddatetime-method-in-Java-with-example-set-1/](https://www.geeksforgeeks.org/hijrahchronology-zoneddatetime-method-in-java-with-example-set-1/)

**Java . time . chrono . hijrah 年表**类的 **zonedDateTime()** 方法用于根据伊斯兰回历从特定时刻检索特定区域的日期和时间。

**语法:**

```
public ChronoZonedDateTime zonedDateTime(Instant instant,
                                         ZoneId zone)

```

**参数**:该方法以下列参数为参数。

*   **瞬间:**哪个是瞬间类型的对象
*   **区域:**是 zoneId 类型的对象

**返回值:**该方法根据伊斯兰回历从特定时刻返回特定区域的日期和时间。

以下是说明**区域时间()**方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

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
            // creating and initializing  HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology used in HijrahDate
            HijrahChronology crono = hidate.getChronology();

            // getting HijrahDate and time for the
            // given Instant and ZoneId
            // by using zonedDateTime() method
            ChronoZonedDateTime<HijrahDate> date
                = crono.zonedDateTime(
                    Instant.now(),
                    ZoneId.systemDefault());

            // display the result
            System.out.println("HijrahDate and time is: "
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

**Output:**

```
HijrahDate and time is: Hijrah-umalqura AH 1441-06-18T13:10:48.843Z[Etc/UTC]

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

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
            // creating and initializing  HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology used in HijrahDate
            HijrahChronology crono = hidate.getChronology();

            // getting HijrahDate and time for the
            // given Instant and ZoneId
            // by using zonedDateTime() method
            ChronoZonedDateTime<HijrahDate> date
                = crono.zonedDateTime(
                    Instant.ofEpochSecond(25000),
                    ZoneId.systemDefault());

            // display the result
            System.out.println("HijrahDate and time is: "
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

**Output:**

```
HijrahDate and time is: Hijrah-umalqura AH 1389-10-22T06:56:40Z[Etc/UTC]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/hijrah 年表. html # zonedDateTime-Java . time . instant-Java . time . zoneid-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#zonedDateTime-java.time.Instant-java.time.ZoneId-)