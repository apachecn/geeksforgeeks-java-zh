# Java 中的带 ZoneSameLocal()方法的时区数据时间，示例

> 原文:[https://www . geeksforgeeks . org/chronozonedattime-witzonesamelocal-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-withzonesamelocal-method-in-java-with-examples/)

一个**时区数据时间**界面的 **withZoneSameLocal()** 方法，用于通过更改时区返回该时区数据时间对象的副本，而不返回即时消息。这种方法基于保持相同的瞬间，因此局部时间线上的间隙和重叠对结果没有影响。

**语法:**

```java
ChronoZonedDateTime withZoneSameLocal(ZoneId zone)

```

**参数:**此方法接受一个单参数**区域**时区更改为。它不应为空。

**返回值:**该方法根据请求区域的日期时间返回一个**时区数据**。

下面的程序说明了 withZoneSameLocal()方法:

**程序 1:**

```java
// Java program to demonstrate
// ChronoZonedDateTime.withZoneSameLocal() method

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

        // apply withZoneSameLocal()
        ChronoZonedDateTime zonedDT2
            = zonedDT
                  .withZoneSameLocal(
                      ZoneId.of("Pacific/Fiji"));

        // print ChronoZonedDateTime after withZoneSameLocal()
        System.out.println("ChronoZonedDateTime of Fuji: "
                           + zonedDT2);
    }
}
```

**输出:**

```java
ChronoZonedDateTime of Calcutta: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
ChronoZonedDateTime of Fuji: 2018-12-06T19:21:12.123+13:00[Pacific/Fiji]

```

**程序二:**

```java
// Java program to demonstrate
// ChronoZonedDateTime.withZoneSameLocal() method

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

        // apply withZoneSameLocal()
        ChronoZonedDateTime zonedDT2
            = zonedDT
                  .withZoneSameLocal(
                      ZoneId.of("Canada/Yukon"));

        // print ChronoZonedDateTime after withZoneSameLocal()
        System.out.println("ChronoZonedDateTime of yukon: "
                           + zonedDT2);
    }
}
```

**输出:**

```java
ChronoZonedDateTime of Calcutta: 2018-10-25T23:12:31.123+02:00[Europe/Paris]
ChronoZonedDateTime of yukon: 2018-10-25T23:12:31.123-07:00[Canada/Yukon]

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/chrono/chronozonaddatetime . html # withzonesamlocal-Java . time . zoneid-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#withZoneSameLocal-java.time.ZoneId-)