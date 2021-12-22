# Java 中的 ChronoLocalDateTime atZone()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-at zone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-atzone-method-in-java-with-examples/)

**计时本地日期时间界面**的 **atZone(ZoneId zone)** 方法用于将该计时本地日期时间与以 ZoneId 为参数的时区相结合，以创建一个 ZonedDateTime 对象。此方法将 ZoneId 作为参数，并在操作返回一个 ChronoZonedDateTime 对象后，将时区与此 ChronoLocalDateTime 组合在一起。

**语法:**

```java
ChronoZonedDateTime<D> atZone(ZoneId zone)
```

**参数:**该方法接受一个参数**区域**，该区域是要组合到该 ChronoLocalDateTime 对象的区域。它不应为空。

**返回值:**该方法返回一个**时区时间**，它是当前时区时间和作为参数传递的时区的组合。

下面的程序说明了 ChronoLocalDateTime.atZone()方法:

**程序 1:**

```java
// Java program to demonstrate
// ChronoLocalDateTime.atZone() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ChronoLocalDateTime object
        ChronoLocalDateTime date
            = LocalDateTime.parse("2018-12-06T19:21:12");

        // print ChronoLocalDateTime Value
        System.out.println("ChronoLocalDateTime: "
                           + date);

        // create ZoneId object
        ZoneId zone = ZoneId.of("Europe/Paris");

        // apply atZone method of ChronoLocalDateTime class
        ChronoZonedDateTime result = date.atZone(zone);

        // print results
        System.out.println("ChronoZonedDateTime: "
                           + result);
    }
}
```

**输出:**

```java
ChronoLocalDateTime: 2018-12-06T19:21:12
ChronoZonedDateTime: 2018-12-06T19:21:12+01:00[Europe/Paris]

```

**程序二:**

```java
// Java program to demonstrate
// ChronoLocalDateTime.atZone() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ChronoLocalDateTime object
        ChronoLocalDateTime date
            = LocalDateTime.parse("2018-12-06T19:21:12");

        // print ChronoLocalDateTime Value
        System.out.println("ChronoLocalDateTime: "
                           + date);

        // create ZoneId object
        ZoneId zone = ZoneId.of("Asia/Aden");

        // apply atZone method
        ChronoZonedDateTime result
            = date.atZone(zone);

        // print results
        System.out.println("ChronoZonedDateTime: "
                           + result);
    }
}
```

**输出:**

```java
ChronoLocalDateTime: 2018-12-06T19:21:12
ChronoZonedDateTime: 2018-12-06T19:21:12+03:00[Asia/Aden]

```

**参考**:[https://docs . Oracle . com/javae/9/docs/API/Java/time/chrono/cron caldatetime . html # atz one-Java . time . zoneid-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#atZone-java.time.ZoneId-)