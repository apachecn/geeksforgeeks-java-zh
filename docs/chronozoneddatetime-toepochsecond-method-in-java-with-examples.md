# Java 中的 ChronoZonedDateTime toEpochSecond()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-toepochssecond-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-toepochsecond-method-in-java-with-examples/)

**时区数据时间**界面的**至**方法用于将该时区数据时间转换为自 1970-01-01T00:00:00Z 纪元以来的秒数。该方法将此时区数据时间与作为参数传递的偏移量相结合，以计算历元秒值，即从 1970-01-01T00:00:00Z 经过的秒数。纪元后时间线上的瞬间是正的，更早的是负的。

**语法:**

```
default long toEpochSecond()

```

**参数:**该方法不接受任何参数。

**返回值:**此方法返回**长**，为 1970-01-01T00:00:00Z 纪元以来的秒数，可能为负数。

以下程序说明了 toEpochSecond()方法:

**程序 1:**

```
// Java program to demonstrate
// ChronoZonedDateTime.toEpochSecond() method

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
        System.out.println("Epoch Second: "
                           + time.toEpochSecond());
    }
}
```

**输出:**

```
ChronoZonedDateTime: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
Epoch Second: 1544104272

```

**程序二:**

```
// Java program to demonstrate
// ChronoZonedDateTime.toEpochSecond() method

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
        System.out.println("Epoch Second: "
                           + time.toEpochSecond());
    }
}
```

**输出:**

```
ChronoZonedDateTime: 1918-10-25T23:12:38.543Z[Europe/Paris]
Epoch Second: -1615250842

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/chrono/chronitorogedatetime . html # topochtsecond】](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#toEpochSecond--)