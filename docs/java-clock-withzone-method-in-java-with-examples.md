# Java 时钟带区()方法在 Java 中带示例

> 原文:[https://www . geesforgeks . org/Java-clock-with zone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/java-clock-withzone-method-in-java-with-examples/)

**Java . time . Clock . with zone(ZoneId zone)**方法是 Clock 类的一个方法，它返回应用了该方法的时钟对象的一个不同时区的时钟副本。如果有一个时钟，需要更改时钟的区域，但不需要更改其他属性，则使用 withZone()方法。此方法将区域作为参数，该参数是需要更改的时区。它返回带有区域的时钟，与参数中传递的区域相同。

**语法:**

```
public abstract Clock withZone(ZoneId zone)
```

**参数:**该方法采用 ZoneId 类型的强制参数**区域**，其中需要更改时区。

**返回:**此方法返回应用此方法的时钟对象的时钟副本，不同的时区作为参数传递。

**示例:**

```
Code:
//Clock with default zone
Clock clock1=Clock.systemUTC();
ZoneId zone = ZoneId.of("Asia/Calcutta");
Clock clock2 = clock1.withZone(zone);
System.out.println(clock2.toString());

Output:: 
SystemClock[Asia/Calcutta]

Explanation:: 
when withZone() is called for Clock object clock1 with zoneId "Asia/Calcutta",
then the withZone() method will return a Clock whose Zone is "Asia/Calcutta".

```

下面的程序说明了 java.time.Clock 类的 withZone()方法:

**程序 1:** 在 withZone()的帮助下，创建一个与第一个时钟具有相似属性但 zoneId 等于“亚洲/加尔各答”的时钟。

```
// Java program to demonstrate
// withZone() method of Clock class

import java.time.*;

// create class
public class withZoneMethodDemo {

    // Main method
    public static void main(String[] args)
    {
        // create a base Clock with systemUTC() method
        Clock baseclock = Clock.systemUTC();

        // get ZonedDateTime object from baseclock
        // clock instant to get date time
        ZonedDateTime baseTime = baseclock
                                     .instant()
                                     .atZone(baseclock.getZone());

        // print details of ZonedDateTime
        System.out.println("ZonedDateTime of baseclock "
                           + baseTime.toString());

        // create ZoneId object with Zone Asia/Calcutta
        ZoneId zone = ZoneId.of("Asia/Calcutta");

        // apply withZone() to change zone from utc to Asia/Calcutta
        Clock clockWithOtherZone = baseclock.withZone(zone);

        // get ZonedDateTime object from clockWithOtherZone
        // clock instant to get date time
        ZonedDateTime calcuttaTime = clockWithOtherZone
                                         .instant()
                                         .atZone(clockWithOtherZone.getZone());

        // print details of ZonedDateTime
        System.out.println("ZonedDateTime of clockWithOtherZone "
                           + calcuttaTime.toString());
    }
}
```

**Output:**

```
ZonedDateTime of baseclock 2018-08-24T08:09:17.354Z
ZonedDateTime of clockWithOtherZone 2018-08-24T13:39:17.539+05:30[Asia/Calcutta]

```

**程序 2:** 使用 getZone()为 withZone()创建的时钟打印 zoneId。

```
// Java program to demonstrate
// withZone() method of Clock class

import java.time.*;

// create class
public class withZoneMethodDemo {

    // Main method
    public static void main(String[] args)
    {
        // create a base Clock with systemDefaultZone() method
        Clock baseclock = Clock.systemDefaultZone();

        // print details of ZonedDateTime
        System.out.println("baseclock Zone:"
                           + baseclock.getZone());

        // create ZoneId object with Zone Asia/Calcutta
        ZoneId zone = ZoneId.of("Asia/Calcutta");

        // apply withZone() to change zone
        // of baseclock to Asia/Calcutta
        Clock clockWithOtherZone = baseclock.withZone(zone);

        // print details of ZonedDateTime
        System.out.println("clockWithOtherZone Zone:"
                           + clockWithOtherZone.getZone());
    }
}
```

**Output:**

```
baseclock Zone:Etc/UTC
clockWithOtherZone Zone:Asia/Calcutta

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/time/clock . html # with zone-Java . time . zoneid-](https://docs.oracle.com/javase/8/docs/api/java/time/Clock.html#withZone-java.time.ZoneId-)