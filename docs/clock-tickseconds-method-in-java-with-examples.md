# Java 中的 Clock ticks()方法，示例

> 原文:[https://www . geesforgeks . org/clock-ticks-method-in-Java-with-examples/](https://www.geeksforgeeks.org/clock-tickseconds-method-in-java-with-examples/)

**Java . time . Clock . tick Seconds(ZoneId zone)**方法是 Clock 类的一个静态方法，该方法返回一个时钟，该时钟使用最佳可用系统时钟返回当前整段秒内的嘀嗒声，并且 instant zone 与作为参数传递的 instant 相同。

返回的时钟也是不可变的、线程安全的和可序列化的，这个方法相当于 tick(system(zone)，Duration.ofSeconds(1))。

**语法:**

```
public static Clock tickSeconds(ZoneId zone)
```

**参数:**该方法取一个强制参数**区域**，该区域是用来舍入整秒内时钟瞬间的时区。

**返回值:**该方法返回一个时钟，该时钟以整秒为单位返回当前的嘀嗒声，区域与作为参数传递的区域相同。

**示例:**

```
Code:
ZoneId zoneId = ZoneId.of("Asia/Calcutta");
Clock clock = Clock.tickSeconds(zoneId);
System.out.println(clock.instant());

Output:
2018-08-21T20:22:32Z

Explanation::
method tickSeconds() returns the instant 
which ticks in a whole Second means 
nanosecond field is zero.

```

下面的程序说明了 java.time.Clock 类的 class()方法:

**程序 1；**当用加尔各答区创建时钟并以整秒为单位打印时钟的滴答声时。

```
// Java program to demonstrate
// tickSeconds() method of Clock class

import java.time.*;

// create class
public class tickSecondsMethodDemo {

    // Main method
    public static void main(String[] args)
    {
        // Zone Id with Zone Asia/Calcutta
        ZoneId zoneId = ZoneId.of("Asia/Calcutta");

        // create a clock which ticks in the whole Second
        Clock clock = Clock.tickSeconds(zoneId);

        // print instance of clock
        System.out.println(clock.instant());
    }
}
```

**Output:**

```
2018-08-22T11:27:38Z

```

**程序 2:** 打印带有欧洲/巴黎区域的时钟日期和时间，以及每秒钟的时钟节拍。

```
// Java program demonstrate
// tickSeconds() method of Clock class

import java.time.*;

// create class
public class tickSecondsMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // Zone Id with Zone Europe/Paris
        ZoneId zoneId = ZoneId.of("Europe/Paris");

        // create a clock which ticks in the whole Second
        Clock clock = Clock.tickSeconds(zoneId);

        // get ZonedDateTime object to print time
        ZonedDateTime time = clock
                                 .instant()
                                 .atZone(clock.getZone());

        // print time variable value
        System.out.println("Date and Time :" + time);
    }
}
```

**Output:**

```
Date and Time :2018-08-22T13:27:41+02:00[Europe/Paris]

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/time/clock . html # tick seconds-Java . time . zoneid-](https://docs.oracle.com/javase/8/docs/api/java/time/Clock.html#tickSeconds-java.time.ZoneId-)