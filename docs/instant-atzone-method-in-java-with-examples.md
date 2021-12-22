# Java 中的 Instant atZone()方法，示例

> 原文:[https://www . geeksforgeeks . org/instant-at zone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-atzone-method-in-java-with-examples/)

**即时类**的 **atZone(ZoneId zone)** 方法用于将该即时与一个时区相结合，该时区的 ZoneId 作为参数给出，以创建一个 ZonedDateTime 对象。此方法将 ZoneId 作为参数，并在操作返回 ZonedDateTime 对象后，将时区与此即时消息相结合。如果瞬间太大，无法放入分区日期时间，那么这个方法将抛出一个异常。该方法与**区域时间间隔(本，区域)**相同。

**语法:**

```
public ZonedDateTime atZone(ZoneId zone)
```

**参数:**该方法接受一个参数**区域**，该区域是要组合到该即时对象的区域。它不应为空。

**返回值:**该方法返回一个**区域时间**，它是当前即时区域和作为参数传递的区域的组合。

**异常:**如果瞬间太大，无法适应分区的日期时间，这个方法抛出**日期时间异常**。

下面的程序说明了 Instant.atZone()方法:

**程序 1:**

```
// Java program to demonstrate
// Instant.atZone() method

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

        // create ZoneId object
        ZoneId zone = ZoneId.of("Europe/Paris");

        // apply atZone method of Instant class
        ZonedDateTime result = instant.atZone(zone);

        // print results
        System.out.println("ZonedDateTime: "
                           + result);
    }
}
```

**输出:**

```
Instant: 2018-10-20T16:55:30Z
ZonedDateTime: 2018-10-20T18:55:30+02:00[Europe/Paris]

```

**程序二:**

```
// Java program to demonstrate
// Instant.atZone() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an instance object
        Instant instant
            = Instant.parse("2018-11-18T06:55:30.00Z");

        // print Instant Value
        System.out.println("Instant: "
                           + instant);

        // create ZoneId object
        ZoneId zone = ZoneId.of("Asia/Aden");

        // apply atZone method
        ZonedDateTime result
            = instant.atZone(zone);

        // print results
        System.out.println("ZonedDateTime: "
                           + result);
    }
}
```

**输出:**

```
Instant: 2018-11-18T06:55:30Z
ZonedDateTime: 2018-11-18T09:55:30+03:00[Asia/Aden]

```

**程序 3:**

```
// Java program to demonstrate
// Instant.atZone() method

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

        // create ZoneId object
        ZoneId zone = ZoneId.of("Pacific/Midway");

        // apply atZone method
        ZonedDateTime result
            = instant.atZone(zone);

        // print results
        System.out.println("ZonedDateTime: "
                           + result);
    }
}
```

**输出:**

```
Instant: 2018-11-22T08:11:48.029Z
ZonedDateTime: 2018-11-21T21:11:48.029-11:00[Pacific/Midway]

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # atZone(Java . time . zoneid)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#atZone(java.time.ZoneId))