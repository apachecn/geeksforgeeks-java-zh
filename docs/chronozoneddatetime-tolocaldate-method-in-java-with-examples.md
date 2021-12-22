# Java 中的 ChronoZonedDateTime toLocalDate()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-to localdate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-tolocaldate-method-in-java-with-examples/)

一个**时区数据时间**类的 **toLocalDate()** 方法用于将该时区数据时间转换为本地日期。

**语法:**

```
default LocalDate toLocalDate()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回**本地日期**，该日期与该时区所代表的本地日期相同。

下面的程序说明了 toLocalDate()方法:

**程序 1:**

```
// Java program to demonstrate
// ChronoZonedDateTime.toLocalDate() method

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
        System.out.println("LocalDate: "
                           + time.toLocalDate());
    }
}
```

**输出:**

```
ChronoZonedDateTime: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
LocalDate: 2018-12-06

```

**程序二:**

```
// Java program to demonstrate
// ChronoZonedDateTime.toLocalDate() method

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
        System.out.println("LocalDate: "
                           + time.toLocalDate());
    }
}
```

**输出:**

```
ChronoZonedDateTime: 1918-10-25T23:12:38.543Z[Europe/Paris]
LocalDate: 1918-10-25

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/chrono/chronitoredatetime . html # tolocaldate--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#toLocalDate--)