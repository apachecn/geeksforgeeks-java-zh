# Java 中的 LocalDate toEpochSecond()方法，示例

> 原文:[https://www . geesforgeks . org/local date-toepchsecond-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-toepochsecond-method-in-java-with-examples/)

**LocalDate** 类的**to pochssecond()**方法用于将该 LocalDate 转换为自 1970-01-01T00:00:00Z 纪元以来的秒数。该方法将此本地日期与作为参数传递的指定时间和偏移量相结合，以计算历元秒值，该值是从 1970-01-01T00:00:00Z 经过的秒数。纪元后时间线上的瞬间是正的，更早的是负的。

**语法:**

```java
public long toEpochSecond(LocalTime time,
                          ZoneOffset offset)

```

**参数:**该方法接受两个参数**时间**和**偏移**，分别是当地时间和区域偏移。

**返回值:**此方法返回**长**，为 1970-01-01T00:00:00Z 纪元以来的秒数，可能为负数。

以下程序说明了 toEpochSecond()方法:

**节目 1:**

```java
// Java program to demonstrate
// LocalDate.toEpochSecond() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate localD
            = LocalDate.parse("2018-12-06");

        // print LocalDate
        System.out.println("LocalDate: "
                           + localD);

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("20:12:32");

        // print Instant
        System.out.println("Passed LocalTime: "
                           + time);

        // create ZoneId
        ZoneOffset zone = ZoneOffset.of("Z");

        // print ZoneId
        System.out.println("Passed ZoneOffset: "
                           + zone);

        // print result
        System.out.println("Epoch Second: "
                           + localD.toEpochSecond(time, zone));
    }
}
```

**输出:**

```java
LocalDate: 2018-12-06
Passed LocalTime: 20:12:32
Passed ZoneOffset: Z
Epoch Second: 1544127152

```

**节目 2:**

```java
// Java program to demonstrate
// LocalDate.toEpochSecond() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate localD
            = LocalDate.parse("2019-01-01");

        // print LocalDate
        System.out.println("LocalDate: "
                           + localD);

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("00:00:00");

        // print Instant
        System.out.println("Passed LocalTime: "
                           + time);

        // create ZoneId
        ZoneOffset zone = ZoneOffset.of("Z");

        // print ZoneId
        System.out.println("Passed ZoneOffset: "
                           + zone);

        // print result
        System.out.println("Epoch Second: "
                           + localD.toEpochSecond(time, zone));
    }
}
```

**输出:**

```java
LocalDate: 2019-01-01
Passed LocalTime: 00:00
Passed ZoneOffset: Z
Epoch Second: 1546300800

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # to pochssecond(Java . time . local time，java.time.ZoneOffset)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#toEpochSecond(java.time.LocalTime, java.time.ZoneOffset))