# Java 中的 LocalDateTime 格式()方法

> 原文:[https://www . geesforgeks . org/local datetime-format-method-in-Java/](https://www.geeksforgeeks.org/localdatetime-format-method-in-java/)

Java 中 **LocalDateTime 类**的 **format()** 方法使用指定的格式化程序格式化这个日期时间。

**语法:**

```
public String format(DateTimeFormatter formatter)

```

**参数:**这个方法接受一个参数*格式化程序*，指定要使用的格式化程序，而不是空值。

**返回:**函数返回格式化的日期字符串，不为空。

下面的程序说明了 LocalDateTime.format()方法:

**程序 1:**

```
// Java program to illustrate the format() method

import java.util.*;
import java.time.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-11-03T12:45:30");

        // Prints the date
        System.out.println("Original LocalDateTime: "
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
Original LocalDateTime: 2018-11-03T12:45:30
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
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDateTime dt1
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

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html #格式(Java . time . format . datetime formatter)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#format(java.time.format.DateTimeFormatter))