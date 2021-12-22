# Java 中的 LocalDateTime 直到()方法，示例

> 原文:[https://www . geesforgeks . org/local datetime-直到 java 中的方法-带示例/](https://www.geeksforgeeks.org/localdatetime-until-method-in-java-with-examples/)

**直到()**类的 **LocalDateTime** 方法，用于使用 TemporalUnit 计算两个 LocalDateTime 对象之间的时间量。起点和终点是这样的，指定的 LocalDateTime 作为参数传递。如果结束在开始之前，结果将是否定的。计算返回一个整数，表示两个 LocalDateTime 之间的完整单位数。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public long until(Temporal endExclusive, TemporalUnit unit)

```

**参数:**该方法接受两个参数 endExclusive，endExclusive 是结束日期，Exclusive 转换为 LocalDateTime，unit 是计量金额的单位。

**返回值:**此方法返回此 LocalDateTime 和结束 LocalDateTime 之间的时间量。

**异常:**该方法抛出以下异常:

*   datetime exception–如果金额无法计算，或者结束时间无法转换为本地日期时间。
*   unsupportedtemporaltypexception–如果设备不受支持。
*   算术异常–如果出现数字溢出。

以下程序说明了直到()方法:
**程序 1:**

```java
// Java program to demonstrate
// LocalDateTime.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDateTime objects
        LocalDateTime l1
            = LocalDateTime
                  .parse("2018-12-06T19:21:12");

        LocalDateTime l2
            = LocalDateTime
                  .parse("2018-10-25T23:12:31.123");

        // apply until method of LocalDateTime class
        long result
            = l2.until(l1,
                       ChronoUnit.MINUTES);

        // print results
        System.out.println("Result in MINUTES: "
                           + result);
    }
}
```

**Output:**

```java
Result in MINUTES: 60248

```

**程序 2:**

```java
// Java program to demonstrate
// LocalDateTime.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDateTime objects
        LocalDateTime l1
            = LocalDateTime
                  .parse("2018-12-06T19:21:12");

        LocalDateTime l2
            = LocalDateTime
                  .parse("2018-10-25T23:12:31.123");

        // applynedDateTime.parseLocalDateTime class
        long result
            = l2.until(l1,
                       ChronoUnit.MONTHS);

        // print results
        System.out.println("Result in MONTHS: "
                           + result);
    }
}
```

**Output:**

```java
Result in MONTHS: 1

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html #直到(java.time.temporal.Temporal，Java . time . temporal alunit)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#until(java.time.temporal.Temporal, java.time.temporal.TemporalUnit))