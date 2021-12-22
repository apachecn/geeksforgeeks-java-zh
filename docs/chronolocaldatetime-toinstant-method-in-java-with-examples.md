# Java 中的 ChronoLocalDateTime toInstant()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-to instant-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-toinstant-method-in-java-with-examples/)

一个**时间位置日期时间**类的**到时间()**方法被用来将这个时间位置日期时间转换成一个时间。该方法将此计时本地日期时间与作为参数传递的偏移量相结合来计算即时时间。

**语法:**

```
default Instant toInstant(ZoneOffset offset)

```

**参数:**该方法接受一个参数**偏移量**，即区域偏移量。

**返回值:**该方法返回**时刻**，即该时间点日期时间的时刻

下面的程序说明了 toInstant()方法:

**程序 1:**

```
// Java program to demonstrate
// ChronoLocalDateTime.toInstant() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoLocalDateTime object
        ChronoLocalDateTime time
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        // print ChronoLocalDateTime
        System.out.println("ChronoLocalDateTime: "
                           + time);

        // create ZoneId
        ZoneOffset zone = ZoneOffset.of("Z");

        // print ZoneId
        System.out.println("Passed ZoneOffset: "
                           + zone);

        // print result
        System.out.println("Instant: "
                           + time.toInstant(zone));
    }
}
```

**输出:**

```
ChronoLocalDateTime: 2019-12-31T19:15:30
Passed ZoneOffset: Z
Instant: 2019-12-31T19:15:30Z

```

**程序二:**

```
// Java program to demonstrate
// ChronoLocalDateTime.toInstant() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoLocalDateTime object
        ChronoLocalDateTime time
            = LocalDateTime.parse(
                "2018-10-25T23:12:31.123");

        // print ChronoLocalDateTime
        System.out.println("ChronoLocalDateTime: "
                           + time);

        // create ZoneId
        ZoneOffset zone = ZoneOffset.of("Z");

        // print ZoneId
        System.out.println("Passed ZoneOffset: "
                           + zone);

        // print result
        System.out.println("Instant: "
                           + time.toInstant(zone));
    }
}
```

**输出:**

```
ChronoLocalDateTime: 2018-10-25T23:12:31.123
Passed ZoneOffset: Z
Instant: 2018-10-25T23:12:31.123Z

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/cron/chronical datetime . html # toconstant-Java . time . zoneoffset-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#toInstant-java.time.ZoneOffset-)