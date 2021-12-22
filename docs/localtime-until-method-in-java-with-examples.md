# Java 中的 LocalTime 直到()方法，示例

> 原文:[https://www . geesforgeks . org/local time-to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-until-method-in-java-with-examples/)

**直到()**方法的 **LocalTime** 类用来计算两个 LocalTime 对象之间的时间量，使用的是 TemporalUnit。起点和终点是这个，指定的 LocalTime 作为参数传递。如果结束在开始之前，结果将是否定的。计算返回一个整数，表示两个 LocalTime 之间的完整单位数。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public long until(Temporal endExclusive, TemporalUnit unit)

```

**参数:**该方法接受两个参数 endExclusive，endExclusive 是结束日期，不含，转换为 LocalTime 和 unit，unit 是计量金额的单位。

**返回值:**此方法返回此 LocalTime 和结束 LocalTime 之间的时间量。

**异常:**该方法抛出以下异常:

*   datetime exception–如果无法计算金额，或者结束时间无法转换为本地时间。
*   unsupportedtemporaltypexception–如果设备不受支持。
*   算术异常–如果出现数字溢出。

以下程序说明了直到()方法:
**程序 1:**

```
// Java program to demonstrate
// LocalTime.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalTime objects
        LocalTime l1
            = LocalTime
                  .parse("19:21:12");

        LocalTime l2
            = LocalTime
                  .parse("23:12:31.123");

        // apply until method of LocalTime class
        long result
            = l2.until(l1,
                       ChronoUnit.SECONDS);

        // print results
        System.out.println("Result in SECONDS: "
                           + result);
    }
}
```

**Output:**

```
Result in SECONDS: -13879

```

**程序 2:**

```
// Java program to demonstrate
// LocalTime.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalTime objects
        LocalTime l1
            = LocalTime
                  .parse("19:21:12");

        LocalTime l2
            = LocalTime
                  .parse("23:12:31.123");

        // applynedDateTime.parseLocalTime class
        long result
            = l1.until(l2,
                       ChronoUnit.HOURS);

        // print results
        System.out.println("Result in HOURS: "
                           + result);
    }
}
```

**Output:**

```
Result in HOURS: 3

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/localtime . html #直到(java.time.temporal.Temporal，Java . time . temporalunit)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#until(java.time.temporal.Temporal, java.time.temporal.TemporalUnit))