# Java 中的时钟滴答()方法，示例

> 原文:[https://www . geesforgeks . org/clock-tick-method-in-Java-with-examples/](https://www.geeksforgeeks.org/clock-tick-method-in-java-with-examples/)

**java.time.Clock** 的 **tick(Clock baseClock，Duration tickDuration)** 方法是 Clock 类的静态方法，它返回一个时钟，**返回从基准时钟舍入到参数中指定持续时间的最近出现点**的瞬间。指定的基准时钟持续时间必须为正，既不为负也不为空。时钟将按照给定的持续时间滴答作响，如果持续时间是半分钟或半秒或半小时，则时钟将返回由持续时间指定的舍入到半分钟或半秒或半小时的瞬间。

这种方法有助于定制根据持续时间打卡的时钟类别。例如，一个刻度表示如果持续时间为 5 秒，则瞬间的第二部分将按照 5 秒四舍五入。如果基准时钟的第二部分是 13，那么它将是 10。舍入时钟返回的时间小于基准时钟。

零或一纳秒的持续时间对基本时钟方法没有影响。这些将返回相同的基准时钟。如果基础时钟是不可变的、线程安全的和可序列化的，那么返回的时钟也将是不可变的、线程安全的和可序列化的。

**语法:**

```java
public static Clock tick(Clock baseClock, Duration tickDuration)
```

**参数:**该方法取两个强制参数:

*   **基准时钟**–根据持续时间要舍入的基准时钟。
*   **滴答持续时间**–每个可见滴答的持续时间，用于舍入时钟，不为负，不为空。

**返回值:**该方法返回一个使用默认区域中最佳可用系统时钟的时钟

**异常:**该方法抛出以下异常:

*   **IllegalArgumentException**–如果持续时间为负，或者某个部分比整个毫秒小得多
    ，因此整个持续时间不能分割为一秒。
*   **算术异常**–如果持续时间太长，无法用纳秒表示。

**示例:**

```java
Code:
Clock baseClock = Clock.systemDefaultZone();
Clock clock = Clock.tick(baseClock, Duration.ofSeconds(10));

Explanation::
method tick() returns the instant which ticks after per 10 sec means the duration 
of the tick is 10sec.is instant actual time is 18:57:51.248Z then due to 10sec duration
it will round to 18:57:50Z and same for 18:59:36.247Z to 18:59:30Z.

```

下面的程序说明了 java.time.Clock 类的 tick()方法

**程序 1:** 用 systemDefaultZone()创建时钟时。

在下面的程序中，有三种情况，持续时间分别为 30 秒、10 秒、3 秒。所以这三种情况都要应用 tick()方法。

```java
// Java program to demonstrate
// tick() method of Clock class

import java.time.*;

// create class
public class tickMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create base Clock with systemDefaultZone() method
        Clock baseclock = Clock.systemDefaultZone();

        // get instant of the base class and print instant
        Instant instant = baseclock.instant();
        System.out.println("Instant of Base class " + instant);

        // apply tick Method for Duration of 30sec and
        // create clock1 and print instant of clock1
        Clock clock1 = Clock.tick(baseclock, Duration.ofSeconds(30));
        System.out.println("Instant of Clock1 " + clock1.instant());

        // apply tick Method for Duration of 10sec and
        // create clock2 and print instant of clock2
        Clock clock2 = Clock.tick(baseclock, Duration.ofSeconds(10));
        System.out.println("Instant of Clock2 " + clock2.instant());

        // apply tick Method for Duration of 3sec and
        // create clock3 and print instant of clock3
        Clock clock3 = Clock.tick(baseclock, Duration.ofSeconds(3));
        System.out.println("Instant of Clock3 " + clock3.instant());
    }
}
```

**Output:**

```java
Instant of Base class 2018-08-22T11:18:11.336Z
Instant of Clock1 2018-08-22T11:18:00Z
Instant of Clock2 2018-08-22T11:18:10Z
Instant of Clock3 2018-08-22T11:18:09Z

```

**程序 2:** 当时长为分钟、小时或天时，打印时钟的瞬间。

```java
// Java program to demonstrate
// tick() method of Clock class

import java.time.*;

// create class
public class tickMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create base Clock with systemUTC() method
        Clock baseclock = Clock.systemUTC();

        // get instant of the base class and print instant
        Instant instant = baseclock.instant();
        System.out.println("Instant of Base class "
                           + instant);

        // apply tick Method for Duration of 10 Minutes
        Clock clock1 = Clock.tick(baseclock,
                                  Duration.ofMinutes(10));
        System.out.println("Instant of Clock1 when duration"
                           + " = 10 minutes is "
                           + clock1.instant());

        // apply tick Method for Duration of 2 hours
        Clock clock2 = Clock.tick(baseclock,
                                  Duration.ofHours(2));
        System.out.println("Instant of Clock2 when duration"
                           + " = 2 hours is "
                           + clock2.instant());

        // apply tick Method for Duration of 5 days
        Clock clock3 = Clock.tick(baseclock,
                                  Duration.ofDays(5));
        System.out.println("Instant of Clock2 when duration"
                           + " = 5 days is "
                           + clock3.instant());
    }
}
```

**Output:**

```java
Instant of Base class 2018-08-22T11:18:15.533Z
Instant of Clock1 when duration = 10 minutes is 2018-08-22T11:10:00Z
Instant of Clock2 when duration = 2 hours is 2018-08-22T10:00:00Z
Instant of Clock2 when duration = 5 days is 2018-08-22T00:00:00Z

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/time/clock . html # tick-Java . time . clock-Java . time . duration-](https://docs.oracle.com/javase/8/docs/api/java/time/Clock.html#tick-java.time.Clock-java.time.Duration-)