# Java 8 时钟固定()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-8-clock-fixed-method-with-examples/](https://www.geeksforgeeks.org/java-8-clock-fixed-method-with-examples/)

java 时钟类是 Java 的日期时间应用编程接口的一部分。Java 日期时间应用编程接口是从 Java 版本 8 中添加的。

clock 类的 fixed()方法返回一个 Clock 对象，Clock 对象返回相同的瞬间。通过调用 **Clock 返回 Clock 对象，fixed(参数)**只返回使用参数指定的相同时刻。返回的类对象是*不可变的、线程安全的和可序列化的*。这种方法的主要用途是在*测试*时，需要的时钟固定在当前时钟的位置。

**语法:**

```java
public static Clock fixed(Instant fixedInstant, ZoneId zone)
```

**参数:**该方法取两个强制参数:

*   **固定时间**–创建时钟对象的即时对象。它不能为空。
*   **区域**–时钟对象的时区。它不能为空。

**返回值:**此方法返回返回相同瞬间的 Clock 对象。

**示例:**

```java
Input:: 
Instance object as parameter : Instant.parse("2018-08-19T16:45:42.00Z");
TimeZone Object as parameter : ZoneId.of("Asia/Calcutta");

Output::
class object: 

Explanation:: 
when Clock.fixed(Instant.parse("2018-08-19T16:45:42.00Z") is called, 
then the fixed() method will return a clock object
in return with fixed time zone and instance.

```

下面的程序说明了 java.time.Clock 类的 fixed()方法:

**程序 1:** 定义区域时使用固定()

```java
// Java program to demonstrate
// fixed() method of Clock class

import java.time.*;

// create class
public class fixedMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create instance of clock class
        Instant instant = Instant.parse("2018-08-19T16:02:42.00Z");

        // create ZoneId object for Asia/Calcutta zone
        ZoneId zoneId = ZoneId.of("Asia/Calcutta");

        // call fixed method
        Clock clock = Clock.fixed(instant, zoneId);

        // print details of clock
        System.out.println(clock.toString());
    }
}
```

**Output:**

```java
FixedClock[2018-08-19T16:02:42Z, Asia/Calcutta]

```

**程序 2:** 使用固定()作为默认区域

```java
// Java program to demonstrate 
// fixed() method of Clock class

import java.time.*;

// create class
public class fixedMethodDemo {

    // Main method
    public static void main(String[] args)
    {
        // create instance of clock class
        Instant instant = Instant.now();

        // create ZoneId for defaultZone which is UTC
        ZoneId zoneId = ZoneId.systemDefault();

        // call fixed method
        Clock clock = Clock.fixed(instant, zoneId);

        // print details of clock
        System.out.println(clock.toString());
    }
}
```

**Output:**

```java
FixedClock[2018-08-21T08:10:32.498Z, Etc/UTC]

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/time/clock . html # fixed-Java . time . instant-Java . time . zoneid-](https://docs.oracle.com/javase/8/docs/api/java/time/Clock.html#fixed-java.time.Instant-java.time.ZoneId-)