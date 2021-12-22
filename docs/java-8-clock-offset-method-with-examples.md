# Java 8 时钟偏移()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-8-clock-offset-method-with-examples/](https://www.geeksforgeeks.org/java-8-clock-offset-method-with-examples/)

java 时钟类是 Java 的日期时间应用编程接口的一部分。Java 日期时间应用编程接口是从 Java 版本 8 中添加的。

offset()方法是 Clock 类的静态方法，它返回一个时钟，该时钟的瞬间等于作为参数传递的时钟瞬间和**特定 Offset 持续时间**的总和。如果添加的持续时间是正的，则返回的时钟表示时钟从基准时钟延迟指定持续时间的瞬间。如果添加的持续时间为负，则返回的时钟早于基准时钟的日期和时间。持续时间为零对基准时钟不起作用，并返回基准时钟。

如果基础时钟是不可变的、线程安全的和可串行化的，那么返回的时钟也是不可变的、线程安全的和可串行化的。

**语法:**

```java
public static Clock offset(Clock baseClock, Duration offsetDuration)
```

**参数:**此方法接受两个强制参数:

*   **Basic clock** -A clock for adding duration. It cannot be null.
*   **offset duration** –the duration added with baseClock. It can't be null.

**返回值:**该方法返回一个时钟，其瞬间等于作为参数传递的时钟瞬间和特定偏移持续时间的总和。

下面的程序说明了 java.time.Clock 类的偏移量(基于时钟的时钟，持续时间偏移量持续时间)方法:

**程序 1:** 当偏移量作为小时传递时。

```java
// Java program to demonstrate offset()
// method of Clock class

import java.time.*;

// create class
public class offsetMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // base Clock with default zone
        Clock realClock = Clock.systemDefaultZone();

        // print current time
        System.out.println("Real clock instant is "
                           + realClock.instant());

        // Creating another clock with offset 0
        Clock clock = Clock.offset(realClock, Duration.ZERO);

        // print new clock
        System.out.println("New clock instant"
                           + " with Duration = 0 is "
                           + clock.instant());

        // Creating the clock with 24 hours positive offset
        clock = Clock.offset(realClock, Duration.ofHours(24));

        // print new clock
        System.out.println("New clock instant"
                           + " with Duration = 24hours is "
                           + clock.instant());

        // Creating the clock with 24 hours negative offset
        clock = Clock.offset(realClock, Duration.ofHours(-24));

        // print new clock
        System.out.println("New clock instant"
                           + " with Duration = -24hours is "
                           + clock.instant());
    }
}
```

**输出:**

```java
Real clock instant is 2018-08-21T09:43:13.519Z
New clock instant with Duration = 0 is 2018-08-21T09:43:13.785Z
New clock instant with Duration = 24hours is 2018-08-22T09:43:13.785Z
New clock instant with Duration = -24hours is 2018-08-20T09:43:13.785Z

```

**程序 2:** 当偏移量以秒和分的形式传递时。

```java
// Java program to demonstrate offset() 
// method of Clock class

import java.time.*;

// create class
public class offsetMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create a Zone Id for Europe/Paris
        ZoneId zoneId = ZoneId.of("Europe/Paris");

        // base Clock with default zone
        Clock realClock = Clock.system(zoneId);

        // print current time
        System.out.println("Real clock instant is "
                           + realClock.instant());

        // Creating the clock with 50 seconds positive offset
        Clock clock = Clock.offset(realClock, Duration.ofSeconds(50));

        // print new clock
        System.out.println("Time after 50 second later"
                           + " than real Clock is " + clock.instant());

        // Creating the clock with 30 minutes positive offset
        clock = Clock.offset(realClock, Duration.ofMinutes(30));

        // print new clock
        System.out.println("Time after 30 minutes later"
                           + " than real Clock is " + clock.instant());
    }
}
```

**输出:**

```java
Real clock instant is 2018-08-21T09:43:18.921Z
Time after 50 second later than real Clock is 2018-08-21T09:44:08.969Z
Time after 30 minutes later than real Clock is 2018-08-21T10:13:18.969Z

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/clock . html # offset-Java . time . clock-Java . time . duration-](https://docs.oracle.com/javase/8/docs/api/java/time/Clock.html#offset-java.time.Clock-java.time.Duration-)