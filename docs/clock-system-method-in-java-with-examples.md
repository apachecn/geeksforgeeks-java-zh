# Java 中的时钟系统()方法，示例

> 原文:[https://www . geesforgeks . org/clock-system-method-in-Java-with-examples/](https://www.geeksforgeeks.org/clock-system-method-in-java-with-examples/)

**Java . time . Clock . system(ZoneID zone)**方法是 Clock 类的静态方法，它返回一个时钟，该时钟使用最佳可用系统时钟返回时钟的当前瞬间，返回时钟的 ZoneId 设置为传递的 ZoneId。如果时钟可用，此方法可以使用 System.currentTimeMillis()或其他更高分辨率的时钟。

在从即时转换为日期或时间时，指定的时区用于给出该时区的日期和时间。从该方法返回的时钟是不可变的、线程安全的和可序列化的。

**语法:**

```java
public static Clock system(ZoneId zone)
```

**参数:**该方法采用强制参数**区域**，该区域是将即时转换为日期时间时使用的时区

**返回:**该方法返回给定区域标识的时钟对象

**示例:**

```java
Code:
// create a Zone Id for Europe/Paris
ZoneId zoneId = ZoneId.of("Europe/Paris");

// base Clock with default zone
Clock realClock=Clock.system(zoneId);
System.out.println(clock.instant());

Output:: 
2018-08-21T10:25:52.361Z

Explanation:: 
when you call system(ZoneId) for Clock then the system(ZoneId)
method will return a Class Object for the given ZoneId.you can get
date and time of clock by using instant of class.

```

下面的程序说明了 java.time.Clock 类的系统(ZoneId)方法:

**程序 1:** 用系统(ZoneId)创建时钟时，其中 ZoneId 为“欧洲/巴黎”，并打印时钟的日期和时间。

```java
// Java program to demonstrate
// system(ZoneId) method of Clock class

import java.time.*;

// create class
public class systemMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create a Zone Id for Europe/Paris
        ZoneId zoneId = ZoneId.of("Europe/Paris");

        // create Clock with system(zoneId) method
        Clock clock = Clock.system(zoneId);

        // get instant of class
        Instant instant = clock.instant();

        // get ZonedDateTime object from instantObj to get date time
        ZonedDateTime time = instant.atZone(clock.getZone());

        // print details of time
        System.out.println("Instant for class is " + time.toString());
    }
}
```

**Output:**

```java
Instant for class is 2018-08-22T13:53:35.779+02:00[Europe/Paris]

```

**程序 2:** 使用系统()创建带“美国/亚利桑那州”区域的时钟，并使用 getZone()打印区域标识。

```java
// Java program to demonstrate
// system(ZoneId) method of Clock class

import java.time.*;

// create class
public class systemMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create a Zone Id for US/Arizona
        ZoneId zoneId = ZoneId.of("US/Arizona");

        // create Clock with system(zoneId) method
        Clock clock = Clock.system(zoneId);

        // print details of ZoneId of new Clock
        System.out.println("ZoneID of class is "
                           + clock.getZone());
    }
}
```

**Output:**

```java
ZoneID of class is US/Arizona

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/time/clock . html # system-Java . time . zoneid-](https://docs.oracle.com/javase/8/docs/api/java/time/Clock.html#system-java.time.ZoneId-)