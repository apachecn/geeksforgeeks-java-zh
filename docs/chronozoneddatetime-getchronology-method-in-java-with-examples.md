# Java 中的 ChronoZonedDateTime()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-get timer-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-getchronology-method-in-java-with-examples/)

Java 中**时区**界面的**获取年表()**方法获取这个日期的年表，就是 ISO 日历系统。

**语法** :

```
default IsoChronology getChronology()

```

**参数**:此方法不接受任何参数。

**返回值**:返回 ISO 年表，不为空。

下面的程序说明了 get()方法:

**程序 1:**

```
// Java program to demonstrate
// ChronoZonedDateTime.get() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoZonedDateTime object
        ChronoZonedDateTime zonedDT
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // print result
        System.out.println("Chronology: "
                           + zonedDT.getChronology());
    }
}
```

**输出:**

```
Chronology: ISO

```

**程序二:**

```
// Java program to demonstrate
// ChronoZonedDateTime.get() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoZonedDateTime object
        ChronoZonedDateTime zonedDT
            = ZonedDateTime.parse(
                "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        System.out.println("Chronology: "
                           + zonedDT.getChronology());
    }
}
```

**输出:**

```
Chronology: ISO

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronozoneddatetime . html # gettimero–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#getChronology--)