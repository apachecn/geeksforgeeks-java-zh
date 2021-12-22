# Java 中的 ChronoLocalDateTime 格式()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-format-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-format-method-in-java-with-examples/)

Java 中**计时本地日期时间接口**的**格式()**方法使用指定的格式化程序格式化该日期时间。

**语法:**

```
default String format(DateTimeFormatter formatter)

```

**参数:**此方法接受一个参数*格式化程序*，该参数指定要使用的日期时间格式化程序，而不是空值。

**返回:**函数返回**格式的日期字符串**，不为空。

下面的程序说明了 ChronoLocalDateTime.format()方法:

**程序 1:**

```
// Java program to illustrate the format() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoLocalDateTime dt1
            = LocalDateTime
                  .parse("2018-11-03T12:45:30");

        // Prints the date
        System.out.println("Original ChronoLocalDateTime: "
                           + dt1);

        // Display d1 in different formats
        // using format() method
        System.out.println("BASIC_ISO_DATE format: "
                           + (DateTimeFormatter.BASIC_ISO_DATE)
                                 .format(dt1));
        System.out.println("ISO_LOCAL_DATE format: "
                           + (DateTimeFormatter.ISO_LOCAL_DATE)
                                 .format(dt1));
        System.out.println("ISO_DATE format: "
                           + (DateTimeFormatter.ISO_DATE)
                                 .format(dt1));
        System.out.println("ISO_LOCAL_TIME format: "
                           + (DateTimeFormatter.ISO_LOCAL_TIME)
                                 .format(dt1));
    }
}
```

**输出:**

```
Original ChronoLocalDateTime: 2018-11-03T12:45:30
BASIC_ISO_DATE format: 20181103
ISO_LOCAL_DATE format: 2018-11-03
ISO_DATE format: 2018-11-03
ISO_LOCAL_TIME format: 12:45:30

```

**程序二:**

```
// Program to illustrate the format() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoLocalDateTime dt1
            = LocalDateTime
                  .parse("2016-09-06T12:45:30");

        // Prints the date
        System.out.println(dt1);

        // Display d1 in different formats
        // using format() method
        System.out.println("ISO_TIME format: "
                           + (DateTimeFormatter.ISO_TIME)
                                 .format(dt1));
        System.out.println("ISO_LOCAL_DATE_TIME format: "
                           + (DateTimeFormatter.ISO_LOCAL_DATE_TIME)
                                 .format(dt1));
        System.out.println("ISO_DATE_TIME format: "
                           + (DateTimeFormatter.ISO_DATE_TIME)
                                 .format(dt1));
        System.out.println("ISO_ORDINAL_DATE format: "
                           + (DateTimeFormatter.ISO_ORDINAL_DATE)
                                 .format(dt1));
        System.out.println("ISO_WEEK_DATE format: "
                           + (DateTimeFormatter.ISO_WEEK_DATE)
                                 .format(dt1));
    }
}
```

**输出:**

```
2016-09-06T12:45:30
ISO_TIME format: 12:45:30
ISO_LOCAL_DATE_TIME format: 2016-09-06T12:45:30
ISO_DATE_TIME format: 2016-09-06T12:45:30
ISO_ORDINAL_DATE format: 2016-250
ISO_WEEK_DATE format: 2016-W36-2

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldatetime . html # format-Java . time . format . datetime formatter-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#format-java.time.format.DateTimeFormatter-)