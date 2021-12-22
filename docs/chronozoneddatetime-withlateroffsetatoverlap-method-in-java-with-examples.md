# Java 中的 time zoneddatetime with lateraoffsettoverlap()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-with lateraoffsetatoverlap-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-withlateroffsetatoverlap-method-in-java-with-examples/)

**时区数据时间**接口的**with lateroffsettoverlap()**方法用于在本地时间线重叠处将时区偏移量更改为两个有效偏移量中的较晚者后，返回该时区数据时间对象的副本。当夏令时结束，一个小时回到时间线时，就会发生重叠。为此，本地日期时间有两个有效的偏移量，调用 withLaterOffsetAtOverlap 方法将返回一个带有两个区域中较晚区域的时区。如果此方法不是重叠时调用，则返回。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
ChronoZonedDateTime withLaterOffsetAtOverlap()

```

**参数:**该方法不接受参数。

**返回值:**该方法根据该日期时间返回一个**时区的时间**，该日期时间有后一个偏移量。

下面的程序说明了 withLaterOffsetAtOverlap()方法:

**程序 1:**

```
// Java program to demonstrate
// ChronoZonedDateTime.withLaterOffsetAtOverlap() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoZonedDateTime object
        ChronoZonedDateTime zonedDT
            = ZonedDateTime.of(
                LocalDateTime.of(2018, 11, 4, 1, 25, 43),
                ZoneId.of("US/Central"));

        // print ChronoZonedDateTime
        System.out.println("Before withLaterOffsetAtOverlap(): "
                           + zonedDT);

        // apply withLaterOffsetAtOverlap()
        ChronoZonedDateTime zonedDT2
            = zonedDT.withLaterOffsetAtOverlap();

        // print ChronoZonedDateTime
        // after withLaterOffsetAtOverlap()
        System.out.println("After withLaterOffsetAtOverlap(): "
                           + zonedDT2);
    }
}
```

**输出:**

```
Before withLaterOffsetAtOverlap(): 2018-11-04T01:25:43-05:00[US/Central]
After withLaterOffsetAtOverlap(): 2018-11-04T01:25:43-06:00[US/Central]

```

**程序二:**

```
// Java program to demonstrate
// ChronoZonedDateTime.withLaterOffsetAtOverlap() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoZonedDateTime object
        ChronoZonedDateTime zonedDT
            = ZonedDateTime.of(
                LocalDateTime.of(2021, 11, 07, 1, 05, 53),
                ZoneId.of("US/Central"));

        // print ChronoZonedDateTime
        System.out.println("Before withLaterOffsetAtOverlap(): "
                           + zonedDT);

        // apply withLaterOffsetAtOverlap()
        ChronoZonedDateTime zonedDT2
            = zonedDT.withLaterOffsetAtOverlap();

        // print ChronoZonedDateTime
        // after withLaterOffsetAtOverlap()
        System.out.println("After withLaterOffsetAtOverlap(): "
                           + zonedDT2);
    }
}
```

**输出:**

```
Before withLaterOffsetAtOverlap(): 2021-11-07T01:05:53-05:00[US/Central]
After withLaterOffsetAtOverlap(): 2021-11-07T01:05:53-06:00[US/Central]

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/chrono/chronitoredatetime . html # withlateralstatverep--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#withLaterOffsetAtOverlap--)