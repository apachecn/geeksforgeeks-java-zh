# Java 中的时钟系统 UTC()方法，示例

> 原文:[https://www . geesforgeks . org/clock-system utc-method-in-Java-with-examples/](https://www.geeksforgeeks.org/clock-systemutc-method-in-java-with-examples/)

**Java . time . Clock . systemutc()**方法是 Clock 类的静态方法，它返回一个时钟，该时钟使用最佳可用系统时钟返回时钟的当前时刻，其中返回时钟的 Zone 是 UTC 时区。

如果需要没有日期或时间的当前即时消息，请使用 systemUTC()方法代替 systemDefaultZone()。

将即时转换为日期和时间时，转换器使用世界协调时时区作为转换区域。该时钟基于最佳可用系统时钟。如果时钟可用，此方法可以使用 System.currentTimeMillis()或其他更高分辨率的时钟来实现。

从该方法返回的时钟是不可变的、线程安全的和可序列化的。

**语法:**

```
public static Clock systemUTC()
```

**返回值:**该方法返回一个时钟，该时钟使用世界协调时时区内最佳可用的系统时钟

**示例:**

```
Code:
//Clock with default zone
Clock clock=Clock.systemUTC();
System.out.println(clock.instant());

Output:: 
2018-08-21T20:38:10.772Z

Explanation:: 
when you call systemUTC() for Clock then the systemUTC()
method will return a Class Object whose Zone is UTC time zone.

```

下面的程序说明了 java.time.Clock 类的 systemUTC()方法:

**程序 1:** 用系统时间创建时钟时()。

这种方法使时钟区域变为世界协调时区域。以下程序以 ZonedDateTime 格式打印时钟的日期和时间。

```
// Java program to demonstrate
// systemUTC() method of Clock class

import java.time.*;

// create class
public class systemUTCMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create Clock with systemUTC() method
        Clock clock = Clock.systemUTC();

        // get instant of class
        Instant instant = clock.instant();

        // get ZonedDateTime object from instantObj
        // to get date time
        ZonedDateTime time = instant.atZone(clock.getZone());

        // print details of ZonedDateTime
        System.out.println("ZonedDateTime of class with UTC"
                           + " Time Zone is "
                           + time.toString());
    }
}
```

**Output:**

```
ZonedDateTime of class with UTC Time Zone is 2018-08-22T11:41:15.554Z

```

**程序 2:** 使用 getZone()为 systemUTC()创建的时钟打印 zoneId。

```
// Java program to demonstrate
// systemUTC() method of Clock class

import java.time.*;

// create class
public class systemUTCMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create Clock with systemUTC() method
        Clock clock = Clock.systemUTC();

        // get ZoneId of Clock
        ZoneId zone = clock.getZone();

        // print details of ZoneId of new Clock
        System.out.println("ZoneID of class is " + zone);
    }
}
```

**Output:**

```
ZoneID of class is Z

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/time/clock . html # systemUTC–](https://docs.oracle.com/javase/8/docs/api/java/time/Clock.html#systemUTC--)