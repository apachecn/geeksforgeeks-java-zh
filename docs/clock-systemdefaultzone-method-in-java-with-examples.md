# Java 中的 Clock systemDefaultZone()方法，示例

> 原文:[https://www . geeksforgeeks . org/clock-system defaultzone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/clock-systemdefaultzone-method-in-java-with-examples/)

**Java . time . Clock . systemdefaultzone()**方法是 Clock 类的静态方法，它返回一个时钟，该时钟使用最佳可用系统时钟返回时钟的当前时刻，其中返回时钟的 Zone 是默认时区。
如果时钟可用，该方法可以使用 System.currentTimeMillis()或其他更高分辨率的时钟来实现。这种方法是**推荐在不需要日期或时间**的情况下，需要当前瞬间时使用。但是如果需要操作日期和时间，那么必须使用 system()方法。此方法类似于 system(ZoneId.systemDefault())。从该方法返回的时钟是不可变的、线程安全的和可序列化的。

**语法:**

```
public static Clock systemDefaultZone()
```

**返回:**该方法返回一个使用默认区域中最佳可用系统时钟的时钟

**示例:**

```
Code:
//Clock with default zone
Clock clock=Clock.systemDefaultZone();
System.out.println(clock.instant());

Output:: 
2018-08-21T10:25:52.361Z

Explanation:: 
when you call systemDefaultZone() for Clock 
then the systemDefaultZone() method will 
return a Class Object whose Zone is default Time Zone.

```

下面的程序说明了 java.time.Clock 类的 systemDefaultZone()方法:

**程序 1:** 用 systemDefaultZone()创建时钟时。

此方法将时钟区域设为默认区域。以下程序以 ZonedDateTime 格式打印时钟的日期和时间。

```
// Java program to demonstrate
// systemDefaultZone() method of Clock class

import java.time.*;

// create class
public class systemDefaultZoneMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create Clock with systemDefaultZone() method
        Clock clock = Clock.systemDefaultZone();

        // get instant of class
        Instant instant = clock.instant();

        // get ZonedDateTime object from
        // instantObj to get date time
        ZonedDateTime time = instant.atZone(clock.getZone());

        // print details of ZonedDateTime
        System.out.println("ZonedDateTime of class"
                           + " with default Zone is "
                           + time.toString());
    }
}
```

**Output:**

```
ZonedDateTime of class with default Zone is 2018-08-22T11:34:36.510Z[Etc/UTC]

```

**程序 2:** 使用 getZone()为 systemDefaultZone()创建的时钟打印 zoneId。

```
// Java program to demonstrate
// systemDefaultZone() method of Clock class

import java.time.*;

// create class
public class systemDefaultZoneMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create Clock with systemDefaultZone() method
        Clock clock = Clock.systemDefaultZone();

        // get ZoneId of Clock
        ZoneId zone = clock.getZone();

        // print details of ZoneId of new Clock
        System.out.println("ZoneID of class is " + zone);
    }
}
```

**Output:**

```
ZoneID of class is Etc/UTC

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/time/clock . html # systemDefaultZone–](https://docs.oracle.com/javase/8/docs/api/java/time/Clock.html#systemDefaultZone--)