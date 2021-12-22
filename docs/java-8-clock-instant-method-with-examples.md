# Java 8 时钟即时()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-8-clock-instant-method-with-examples/](https://www.geeksforgeeks.org/java-8-clock-instant-method-with-examples/)

java 时钟类是 Java 的日期时间应用编程接口的一部分。Java 日期时间应用编程接口是从 Java 版本 8 中添加的。

Clock 类的 instant()方法返回 Clock 对象的当前瞬间作为 instant 类对象。Instant 生成一个时间戳来表示机器时间。所以这个方法为 clock 对象生成一个时间戳。这里返回的 Instant 是 java.time.Instant 类的对象，它表示世界协调时区域中时间线上的特定时刻。该时间线是从世界协调时 1970 年第一时刻算起的纳秒数。由于现在大多数业务逻辑、数据存储和数据交换都应该使用 UTC，因此使用 Instant 非常有用。

**语法:**

```java
public abstract Instant instant()
```

**返回值:**该方法返回时钟对象当前的**时刻**。

**异常:**如果无法获得时钟对象的瞬间，该方法抛出**日期时间异常**。

**示例:**

```java
Input:: 
a clock class Object e.g Clock.systemDefaultZone()

Output::
instant  e.g. 2018-08-19T20:22:23.366Z

Explanation:: 
when instant() is called, it returns a current instant of Clock Class Object. 

```

下面的程序说明了 java.time.Clock 类的 instant()方法:

**程序 1** :使用 instant()获取 systemDefaultZone 的时钟对象

```java
// Java Program to demonstrate
// instant() method of Clock class

import java.time.*;

// create class
public class instantMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create Clock Object
        Clock clock = Clock.systemDefaultZone();

        // get Instant Object of Clock
        // object using instant() method
        Instant instantObj = clock.instant();

        // print details of Instant Object
        System.out.println("Instant for class " + clock
                           + " is " + instantObj);
    }
}
```

**Output:**

```java
Instant for class SystemClock[Etc/UTC] is 2018-08-21T05:31:10.662Z

```

**程序 2** :使用 instant()获取带“欧洲/巴黎”区域的时钟对象

要获取基于区域的日期和时间，请通过使用 **atZone(区域标识区域)**打印该区域的日期和时间，从即时获取区域数据时间对象。

**语法:**

```java
// get ZonedDateTime object from instant object returned by instant() method of Clock class
ZonedDateTime time = Clock.systemDefaultZone().instant().atZone(Clock.getZone());

```

**代码:**

```java
// Java Program to demonstrate
// instant() method of Clock class

import java.time.*;

// create class
public class instantMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create a Zone Id for Europe/Paris
        ZoneId zoneId = ZoneId.of("Europe/Paris");

        // create Clock Object by passing zoneID
        Clock clock = Clock.system(zoneId);

        // get Instant Object of Clock
        // object using instant() method
        Instant instantObj = clock.instant();

        // get ZonedDateTime object from
        // instantObj to get zonal date time
        ZonedDateTime time = instantObj.atZone(clock.getZone());

        // print details of Instant Object
        System.out.println("Instant for class " + clock
                           + " is " + time.toString());
    }
}
```

**Output:**

```java
Instant for class SystemClock[Europe/Paris] is 2018-08-21T07:31:13.525+02:00[Europe/Paris]

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/time/clock . html # instant–](https://docs.oracle.com/javase/8/docs/api/java/time/Clock.html#instant--)