# Java 中的 Instant atOffset()方法，示例

> 原文:[https://www . geesforgeks . org/instant-atoffset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-atoffset-method-in-java-with-examples/)

**即时类**的**atOffset(ZoneOffset offset)**方法用于将该即时与一个偏移量相结合，以创建一个 OffsetDateTime 对象。此方法将 ZoneOffset 作为一个参数来返回一个 OffsetDateTime 对象，并且此 OffsetDataTime 对象从此时刻开始，在从 UTC/格林威治的指定偏移量处形成。如果瞬间太大，无法适应偏移日期时间，则该方法将引发异常。这个方法和 **OffsetDateTime.ofInstant(这个，offset)** 一样。

**语法:**

```java
public OffsetDateTime atOffset(ZoneOffset offset)
```

**参数:**
该方法接受一个参数 **offset** ，即与该即时对象结合的区域 offset。它不应该为空

**返回值:**该方法返回从该时刻开始形成的**偏移日期时间**和指定的区域偏移。

**异常:**如果瞬间太大，无法适应偏移日期时间，此方法将抛出**日期时间异常**。

下面的程序说明了 Instant.atOffset()方法:
**程序 1:**

```java
// Java program to demonstrate
// Instant.atOffset() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an instance object
        Instant instant
            = Instant.parse("2018-10-20T16:55:30.00Z");

        // print Instant Value
        System.out.println("Instant: "
                           + instant);

        // create a ZoneOffset object
        // with 7200 sec means 2 hours
        ZoneOffset offset = ZoneOffset.ofTotalSeconds(7200);

        // apply atOffset method to combine ZoneOffset
        // to this instant
        OffsetDateTime offsetDate = instant.atOffset(offset);

        // print results
        System.out.println("Offset Date and Time: "
                           + offsetDate);
    }
}
```

**Output:**

```java
Instant: 2018-10-20T16:55:30Z
Offset Date and Time: 2018-10-20T18:55:30+02:00

```

**程序 2:**

```java
// Java program to demonstrate
// Instant.atOffset() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an instance object
        Instant instant
            = Instant.parse("2018-10-20T16:55:30.00Z");

        // print Instant Value
        System.out.println("Instant: "
                           + instant);

        // create a ZoneOffset object
        // with 3 hours 45 minutes
        ZoneOffset offset
            = ZoneOffset.ofHoursMinutes(3, 45);

        // apply atOffset method to combine ZoneOffset
        // to this instant
        OffsetDateTime offsetDate
            = instant.atOffset(offset);

        // print results
        System.out.println("Offset Date and Time: "
                           + offsetDate);
    }
}
```

**Output:**

```java
Instant: 2018-10-20T16:55:30Z
Offset Date and Time: 2018-10-20T20:40:30+03:45

```

**程序 3:**

```java
// Java program to demonstrate
// Instant.atOffset() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an instance object
        Instant instant
            = Instant.now();

        // print Instant Value
        System.out.println("Instant: "
                           + instant);

        // create a ZoneOffset Object
        // with 9 hours 45 minutes 30 second
        ZoneOffset offset
            = ZoneOffset
                  .ofHoursMinutesSeconds(9, 45, 30);

        // apply atOffset method to
        // combine ZoneOffset to this instant
        OffsetDateTime offsetDate
            = instant.atOffset(offset);

        // print results
        System.out.println("Offset Date and Time: "
                           + offsetDate);
    }
}
```

**Output:**

```java
Instant: 2018-11-22T08:22:19.846Z
Offset Date and Time: 2018-11-22T18:07:49.846+09:45:30

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # atOffset(Java . time . zoneoffset)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#atOffset(java.time.ZoneOffset))