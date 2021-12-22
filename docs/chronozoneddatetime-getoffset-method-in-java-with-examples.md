# Java 中的 ChronoZonedDateTime getOffset()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-get offset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-getoffset-method-in-java-with-examples/)

Java 中**时区数据**界面的 **getOffset()** 方法获取该日期的时区偏移量。

**语法** :

```
default ZoneOffset getOffset()

```

**参数**:此方法不接受任何参数。

**返回值**:返回区域偏移量，不为空。

下面的程序说明了 get()方法:

**程序 1:**

```
// Java program to demonstrate
// ChronoZonedDateTime.getOffset() method

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
        System.out.println("Offset: "
                           + zonedDT.getOffset());
    }
}
```

**输出:**

```
Offset: +05:30

```

**程序二:**

```
// Java program to demonstrate
// ChronoZonedDateTime.getOffset() method

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

        System.out.println("Offset: "
                           + zonedDT.getOffset());
    }
}
```

**输出:**

```
Offset: +02:00

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/chrono/chronitoredatetime . html # getffset】](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#getOffset--)