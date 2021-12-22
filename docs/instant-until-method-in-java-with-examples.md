# Java 中的即时直到()方法，示例

> 原文:[https://www . geesforgeks . org/instant-to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-until-method-in-java-with-examples/)

**直到()**一个 **Instant** 类的方法，用于使用 TemporalUnit 计算两个 Instant 对象之间的时间量。起点和终点是这个，指定的瞬间作为参数传递。如果结束在开始之前，结果将是否定的。计算返回一个整数，表示两个瞬间之间的完整单位数。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public long until(Temporal endExclusive, TemporalUnit unit)

```

**参数:**该方法接受两个参数 **endExclusive** 为结束日期，不包括转换为即时的**单位**为计量金额的单位。

**返回值:**该方法返回本瞬间到结束瞬间之间的时间量。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果金额无法计算，或者结束时间无法转换为即时。
*   **不支持的 temporaltypexception**–如果不支持该设备。
*   **算术异常**–如果出现数值溢出。

以下程序说明了直到()方法:
**程序 1:**

```
// Java program to demonstrate
// Instant.until() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create Instant objects
        Instant instant1
            = Instant.parse("2019-01-03T19:35:50.00Z");
        Instant instant2
            = Instant.parse("2019-01-04T13:18:59.00Z");

        // apply until method of Instant class
        long result
            = instant1.until(instant2,
                             ChronoUnit.MINUTES);

        // print results
        System.out.println("Result in Minutes: "
                           + result);
    }
}
```

**Output:**

```
Result in Minutes: 1063

```

**程序 2:**

```
// Java program to demonstrate
// Instant.until() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create Instant objects
        Instant instant1
            = Instant.parse("2010-01-03T19:35:50.00Z");
        Instant instant2
            = Instant.parse("2019-01-04T13:18:59.00Z");

        // apply until method of Instant class
        long result
            = instant1.until(instant2,
                             ChronoUnit.DAYS);

        // print results
        System.out.println("Result in DAYS: "
                           + result);
    }
}
```

**Output:**

```
Result in DAYS: 3287

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html #直到(java.time.temporal.Temporal，Java . time . temporal alunit)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#until(java.time.temporal.Temporal, java.time.temporal.TemporalUnit))