# Java 中的 ChronoZonedDateTime toLocalTime()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-to localtime-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-tolocaltime-method-in-java-with-examples/)

**时区数据时间**类的 **toLocalTime()** 方法用于将该时区数据时间转换为本地时间。

**语法:**

```
default LocalTime toLocalTime()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回**本地时间**，与该时区所代表的本地时间相同。

下面的程序说明了 toLocalTime()方法:

**程序 1:**

```
// Java program to demonstrate
// ChronoZonedDateTime.toLocalTime() method

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
        System.out.println("LocalTime: "
                           + time.toLocalTime());
    }
}
```

**输出:**

```
ChronoZonedDateTime: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
LocalTime: 19:21:12.123

```

**程序二:**

```
// Java program to demonstrate
// ChronoZonedDateTime.toLocalTime() method

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
        System.out.println("LocalTime: "
                           + time.toLocalTime());
    }
}
```

**输出:**

```
ChronoZonedDateTime: 1918-10-25T23:12:38.543Z[Europe/Paris]
LocalTime: 23:12:38.543

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/chrono/chronitoredatetime . html # tolocaltime--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#toLocalTime--)