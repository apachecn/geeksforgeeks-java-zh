# Java 中的带 withEarlierOffsetAtOverlap()方法的 ChronoZonedDateTime 示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-witharlieoffsetatoverlap-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-withearlieroffsetatoverlap-method-in-java-with-examples/)

**时区数据时间**接口的**witharlieroffsettoverlap()**方法用于在本地时间线重叠处将时区偏移量更改为两个有效偏移量中较早的一个后，返回该时区数据时间对象的副本。当夏令时结束，一个小时回到时间线时，就会发生重叠。因此，本地日期时间有两个有效的偏移量，用 withEarlierOffsetAtOverlap 方法调用将返回一个带有两个区域中较早的一个的计时区域。如果此方法不是重叠时调用，则返回。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
ChronoZonedDateTime withEarlierOffsetAtOverlap()

```

**参数:**该方法不接受参数。

**返回值:**该方法根据该日期时间返回一个**时区时间**，偏移时间较早。

下面的程序说明了 withEarlierOffsetAtOverlap()方法:

**程序 1:**

```java
// Java program to demonstrate
// withEarlierOffsetAtOverlap() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoZonedDateTime object
        ChronoZonedDateTime zonedDT
            = ZonedDateTime
                  .ofLocal(
                      LocalDateTime.of(2018, 11, 4, 1, 25, 43),
                      ZoneId.of("US/Central"),
                      ZoneOffset.ofHours(-6));

        // print ChronoZonedDateTime
        System.out.println("Before"
                           + " withEarlierOffsetAtOverlap():\n "
                           + zonedDT);

        // apply withEarlierOffsetAtOverlap()
        ChronoZonedDateTime zonedDT2
            = zonedDT.withEarlierOffsetAtOverlap();

        // print ChronoZonedDateTime after
        // withEarlierOffsetAtOverlap()
        System.out.println("\nAfter"
                           + " withEarlierOffsetAtOverlap():\n "
                           + zonedDT2);
    }
}
```

**输出:**

```java
Before withEarlierOffsetAtOverlap():
 2018-11-04T01:25:43-06:00[US/Central]

After withEarlierOffsetAtOverlap():
 2018-11-04T01:25:43-05:00[US/Central]

```

**程序二:**

```java
// Java program to demonstrate
// withEarlierOffsetAtOverlap() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoZonedDateTime object
        ChronoZonedDateTime zonedDT
            = ZonedDateTime
                  .ofLocal(
                      LocalDateTime.of(2021, 11, 07, 1, 05, 53),
                      ZoneId.of("US/Central"),
                      ZoneOffset.ofHours(-6));

        // print ChronoZonedDateTime
        System.out.println("Before"
                           + " withEarlierOffsetAtOverlap():\n "
                           + zonedDT);

        // apply withEarlierOffsetAtOverlap()
        ChronoZonedDateTime zonedDT2
            = zonedDT.withEarlierOffsetAtOverlap();

        // print ChronoZonedDateTime after
        // withEarlierOffsetAtOverlap()
        System.out.println("\nAfter"
                           + " withEarlierOffsetAtOverlap():\n "
                           + zonedDT2);
    }
}
```

**输出:**

```java
Before withEarlierOffsetAtOverlap():
 2021-11-07T01:05:53-06:00[US/Central]

After withEarlierOffsetAtOverlap():
 2021-11-07T01:05:53-05:00[US/Central]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronozoneddatetime . html # witharrieoffsetatoverlap–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#withEarlierOffsetAtOverlap--)