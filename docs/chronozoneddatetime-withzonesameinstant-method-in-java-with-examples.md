# 带 ZoneSameInstant()方法的时间区域带示例的 Java】

> 原文:[https://www . geeksforgeeks . org/chronozonedattime-witzonesameinstant-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-withzonesameinstant-method-in-java-with-examples/)

一个**时区数据时间**界面的**withouzonesameinstant()**方法，用于通过更改时区和不带即时信息返回该时区数据时间对象的副本。这种方法基于保持相同的瞬间，因此局部时间线上的间隙和重叠对结果没有影响。

**语法:**

```
ChronoZonedDateTime withZoneSameInstant(ZoneId zone)

```

**参数:**此方法接受一个单参数**区域**时区更改为。它不应为空。

**返回值:**该方法根据请求区域的日期时间返回一个**时区数据**。

**异常:**此方法抛出**日期时间异常**:如果结果超出支持的日期范围。

下面的程序说明了 withZoneSameInstant()方法:

**程序 1:**

```
// Java program to demonstrate
// ChronoZonedDateTime.withZoneSameInstant() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoZonedDateTime object
        ChronoZonedDateTime zonedDT
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // print ChronoZonedDateTime
        System.out.println("ChronoZonedDateTime of Calcutta: "
                           + zonedDT);

        // apply withZoneSameInstant()
        ChronoZonedDateTime zonedDT2
            = zonedDT
                  .withZoneSameInstant(
                      ZoneId.of("Pacific/Fiji"));

        // print ChronoZonedDateTime after withZoneSameInstant()
        System.out.println("ChronoZonedDateTime of Fuji: "
                           + zonedDT2);
    }
}
```

**输出:**

```
ChronoZonedDateTime of Calcutta: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
ChronoZonedDateTime of Fuji: 2018-12-07T02:51:12.123+13:00[Pacific/Fiji]

```

**程序二:**

```
// Java program to demonstrate
// ChronoZonedDateTime.withZoneSameInstant() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoZonedDateTime object
        ChronoZonedDateTime zonedDT
            = ZonedDateTime
                  .parse(
                      "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // print ChronoZonedDateTime
        System.out.println("ChronoZonedDateTime of Calcutta: "
                           + zonedDT);

        // apply withZoneSameInstant()
        ChronoZonedDateTime zonedDT2
            = zonedDT
                  .withZoneSameInstant(
                      ZoneId.of("Canada/Yukon"));

        // print ChronoZonedDateTime after withZoneSameInstant()
        System.out.println("ChronoZonedDateTime of yukon: "
                           + zonedDT2);
    }
}
```

**输出:**

```
ChronoZonedDateTime of Calcutta: 2018-10-25T23:12:31.123+02:00[Europe/Paris]
ChronoZonedDateTime of yukon: 2018-10-25T14:12:31.123-07:00[Canada/Yukon]

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/chrono/chronozonaddatetime . html # withzonesaminstant-Java . time . zoneid-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#withZoneSameInstant-java.time.ZoneId-)