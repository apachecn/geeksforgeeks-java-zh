# Java 中的 Java Clock tickMinutes()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-clock-tick minutes-method-in-Java-with-examples/](https://www.geeksforgeeks.org/java-clock-tickminutes-method-in-java-with-examples/)

**Java . time . Clock . tick minutes(ZoneId zone)**方法是 Clock 类的一个静态方法，它使用最佳可用系统时钟返回当前整分钟的嘀嗒声，并且该时刻的时区与作为参数传递的时区相同。

时钟的纳秒和秒字段设置为零，以整分钟为单位对瞬间进行舍入。底层时钟是最好的系统时钟，与系统时钟(ZoneId)相同。零或一纳秒的持续时间对基本时钟方法没有影响。这些将返回相同的基准时钟。

返回的时钟也是不可变的、线程安全的和可序列化的，这个方法相当于 tick(system(zone)，Duration.ofMinutes(1))。

**语法:**

```
public static Clock tickMinutes(ZoneId zone)
```

**参数:**该方法取一个强制参数**区域**，该区域是用来舍入整分钟内时钟瞬间的时区。

**返回值:**该方法返回一个时钟，该时钟以整分钟为单位返回当前的嘀嗒声
，区域与作为参数传递的区域相同。

**示例:**

```
Code:
ZoneId zoneId = ZoneId.of("Asia/Calcutta");
Clock clock = Clock.tickMinutes(zoneId);
System.out.println(clock.instant());

Output:
2018-08-21T19:55:00Z

Explanation::
method tickMinutes() returns the instant 
which ticks in a whole minute. It means the second
and nanosecond fields are zero, which can be 
visualized as the second field is empty in output.

```

下面的程序说明了 java.time.Clock 类的 tickMinutes()方法:

**程序 1:** 当时钟创建时，带有“亚洲/加尔各答”区域，用于打印整分钟内的时钟滴答声。

```
// Java program to demonstrate
// tickMinutes() method of Clock class

import java.time.*;

// create class
public class GFG {

    // Main method
    public static void main(String[] args)
    {
        // Zone Id with Zone Asia/Calcutta
        ZoneId zoneId = ZoneId.of("Asia/Calcutta");

        // create a clock which ticks in whole minute
        Clock clock = Clock.tickMinutes(zoneId);

        // print instance of clock
        System.out.println(clock.instant());
    }
}
```

**Output:**

```
2018-08-24T07:51:00Z

```

**程序 2:** 打印带有“欧洲/巴黎”区域的时钟日期和时间，以及整分钟的时钟滴答声。

```
// Java program to demonstrate
// tickMinutes() method of Clock class

import java.time.*;

// create class
public class tickMinutesMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // Zone Id with Zone Europe/Paris
        ZoneId zoneId = ZoneId.of("Europe/Paris");

        // create a clock which ticks in whole minute
        Clock clock = Clock.tickMinutes(zoneId);

        // get ZonedDateTime object to print time
        ZonedDateTime time = clock.instant()
                                 .atZone(clock.getZone());

        // print time variable value
        System.out.println("Date and Time :" + time);
    }
}
```

**Output:**

```
Date and Time :2018-08-24T09:52+02:00[Europe/Paris]

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/time/clock . html # tick minutes-Java . time . zoneid-](https://docs.oracle.com/javase/8/docs/api/java/time/Clock.html#tickMinutes-java.time.ZoneId-)