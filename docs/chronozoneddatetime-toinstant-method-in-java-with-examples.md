# Java 中的 ChronoZonedDateTime toInstant()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-to instant-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-toinstant-method-in-java-with-examples/)

一个**时区数据时间**类的**到瞬间()**方法用于将这个时区数据时间转换为瞬间。

**语法:**

```
default Instant toInstant()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回**瞬间**，与该时区所代表的瞬间相同。

下面的程序说明了 toInstant()方法:

**程序 1:**

```
// Java program to demonstrate
// ChronoZonedDateTime.toInstant() method

import java.time.*;
import java.time.chrono.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoZonedDateTime object
        ChronoZonedDateTime time
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // print ChronoZonedDateTime
        System.out.println("ChronoZonedDateTime: "
                           + time);

        // print result
        System.out.println("Instant: "
                           + time.toInstant());
    }
}
```

**输出:**

```
ChronoZonedDateTime: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
Instant: 2018-12-06T13:51:12.123Z

```

**程序二:**

```
// Java program to demonstrate
// ChronoZonedDateTime.toInstant() method

import java.time.*;
import java.time.chrono.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoZonedDateTime object
        ChronoZonedDateTime time
            = ZonedDateTime.parse(
                "1918-10-25T23:12:38.543+02:00[Europe/Paris]");

        // print ChronoZonedDateTime
        System.out.println("ChronoZonedDateTime: "
                           + time);

        // print result
        System.out.println("Instant: "
                           + time.toInstant());
    }
}
```

**输出:**

```
ChronoZonedDateTime: 1918-10-25T23:12:38.543Z[Europe/Paris]
Instant: 1918-10-25T23:12:38.543Z

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/chrono/chronitoredatetime . html # toconstant】](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#toInstant--)