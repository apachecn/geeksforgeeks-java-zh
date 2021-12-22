# Java 中的 LocalDate 直到(时态，临时)方法，示例

> 原文:[https://www . geesforgeks . org/local date-untltemporaltemporalunit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-untiltemporaltemporalunit-method-in-java-with-examples/)

**直到()**方法的 **LocalDate** 类用来计算两个 LocalDate 对象之间的时间量，使用的是 TemporalUnit。起点和终点是这个，指定的 LocalDate 作为参数传递。如果结束在开始之前，结果将是否定的。计算返回一个整数，代表两个 LocalDate 之间的完整单位数。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public long until(Temporal endExclusive, TemporalUnit unit)

```

**参数:**该方法接受两个参数 endExclusive，endExclusive 为结束日期，Exclusive 转换为 LocalDate，unit 为计量金额的单位。

**返回值:**此方法返回此 LocalDate 和结束 LocalDate 之间的时间量。

**异常:**该方法抛出以下异常:

*   datetime exception–如果无法计算金额，或者结束时态无法转换为本地日期。
*   unsupportedtemporaltypexception–如果设备不受支持。
*   算术异常–如果出现数字溢出。

以下程序说明了直到()方法:
**程序 1:**

```java
// Java program to demonstrate
// LocalDate.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDate objects
        LocalDate l1
            = LocalDate
                  .parse("2018-12-06");

        LocalDate l2
            = LocalDate
                  .parse("2018-10-25");

        // apply until the method of LocalDate class
        long result
            = l2.until(l1,
                       ChronoUnit.DAYS);

        // print results
        System.out.println("Result in DAYS: "
                           + result);
    }
}
```

**Output:**

```java
Result in DAYS: 42

```

**程序 2:**

```java
// Java program to demonstrate
// LocalDate.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDate objects
        LocalDate l1
            = LocalDate
                  .parse("2018-12-06");

        LocalDate l2
            = LocalDate
                  .parse("2018-10-25");

        // apply until()
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

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html #直到(java.time.temporal.Temporal，Java . time . temporal alunit)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#until(java.time.temporal.Temporal, java.time.temporal.TemporalUnit))