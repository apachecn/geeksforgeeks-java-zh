# Java 中的 LocalTime toEpochSecond()方法，示例

> 原文:[https://www . geesforgeks . org/local time-toepchsecond-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-toepochsecond-method-in-java-with-examples/)

**LocalTime 类**的**to pochssecond()**方法用于将该 LocalTime 转换为 1970-01-01T00:00:00Z 纪元以来的秒数。该方法将该本地时间与作为参数传递的指定日期和偏移量相结合，以计算历元秒值，该值是从 1970-01-01T00:00:00Z 经过的秒数。纪元后时间线上的瞬间是正的，更早的是负的。

**语法:**

```
public long 
         toEpochSecond(LocalDate date,
                          ZoneOffset offset)

```

**参数:**该方法接受两个参数:

*   **Date:** is the target date used for epoch second calculation.
*   **Offset:** is the regional offset.

**返回值:**此方法返回 1970-01-01T00:00:00Z 纪元以来的**秒数**。可能是负面的。

以下程序说明了 toEpochSecond()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalTime.toEpochSecond() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate date
            = LocalDate.parse("2018-12-29");

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("20:12:32");

        // print Instant
        System.out.println("LocalDate: " + date);

        // create ZoneId
        ZoneOffset zone = ZoneOffset.of("Z");

        // print ZoneId
        System.out.println("ZoneOffset: " + zone);

        // apply ofInstant()
        long value = time.toEpochSecond(date, zone);

        // print result
        System.out.println("Epoch Second: "
                           + value);
    }
}
```

**输出:**

```
LocalDate: 2018-12-29
ZoneOffset: Z
Epoch Second: 1546114352

```

**程序二:**

```
// Java program to demonstrate
// LocalTime.toEpochSecond() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate date
            = LocalDate.parse("1909-04-18");

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("00:10:09");

        // print Instant
        System.out.println("LocalDate: " + date);

        // create ZoneId
        ZoneOffset zone = ZoneOffset.of("Z");

        // print ZoneId
        System.out.println("ZoneOffset: " + zone);

        // apply ofInstant()
        long value = time.toEpochSecond(date, zone);

        // print result
        System.out.println("Epoch Second: "
                           + value);
    }
}
```

**输出:**

```
LocalDate: 1909-04-18
ZoneOffset: Z
Epoch Second: -1915746591

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # to pochssecond(Java . time . local date，java.time.ZoneOffset)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#toEpochSecond(java.time.LocalDate, java.time.ZoneOffset))