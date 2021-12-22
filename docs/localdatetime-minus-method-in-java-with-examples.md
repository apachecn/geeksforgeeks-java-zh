# Java 中的 LocalDateTime 减()方法，示例

> 原文:[https://www . geesforgeks . org/local datetime-减去方法-in-java-with-examples/](https://www.geeksforgeeks.org/localdatetime-minus-method-in-java-with-examples/)

在 LocalDateTime 类中，根据传递给它的参数，有两种类型的减()方法。

### 减(长数量到子管道，临时单位)

**减()**一个 **LocalDateTime** 类的方法，用于返回这个 LocalDateTime 的一个副本，并减去指定数量的单位。如果由于不支持该单位或其他原因而无法减去该金额，则会引发异常。

**语法:**

```java
public LocalDateTime minus(long amountToSubtract,
                           TemporalUnit unit)

```

**参数:**该方法接受两个参数 **amountToSubtract** 可以为负数，也可以接受**单位**为要减去的量的单位，不为空。

**返回值:**该方法基于该 LocalDateTime 返回 **LocalDateTime** ，减去指定的金额。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行减法运算
*   **不支持的 temporaltypexception**–如果不支持该设备
*   **算术异常**–如果出现数值溢出

下面的程序说明了减()方法:
**程序 1:**

```java
// Java program to demonstrate
// LocalDateTime.minus() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // Get the LocalDateTime instance
        LocalDateTime ldt
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        // Get the String representation of this LocalDateTime
        System.out.println("Original LocalDateTime: "
                           + ldt.toString());

        // subtract 200 DAYS to LocalDateTime
        LocalDateTime value
            = ldt.minus(200, ChronoUnit.DAYS);

        // print result
        System.out.println("LocalDateTime after subtracting DAYS: "
                           + value);
    }
}
```

**Output:**

```java
Original LocalDateTime: 2019-12-31T19:15:30
LocalDateTime after subtracting DAYS: 2019-06-14T19:15:30

```

### 减(临时金额到小计)

**减去()**方法的一个 **LocalDateTime** 类用来返回这个 LocalDateTime 的一个副本，指定的数量减去日期时间。该金额通常为“期间”或“持续时间”，但也可以是实现临时计费界面的任何其他类型。

**语法:**

```java
public LocalDateTime minus(TemporalAmount amountTosubtract)

```

**参数:**此方法接受一个单参数 **amountTosubtract** 为要减去的量，不应为空。

**返回值:**该方法基于该日期时间进行减法运算，返回**本地日期时间**，不为空。

**异常:**
此方法抛出以下异常:

*   **日期时间异常**–如果无法进行减法运算
*   **算术异常**–如果出现数值溢出

下面的程序说明了减()方法:
**程序 1:**

```java
// Java program to demonstrate
// LocalDateTime.minus() method

import java.time.*;
public class GFG {
    public static void main(String[] args)
    {

        // Get the LocalDateTime instance
        LocalDateTime ldt
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        // Get the String representation of this LocalDateTime
        System.out.println("Original LocalDateTime: "
                           + ldt.toString());

        // subtract 10 Days to LocalDateTime
        LocalDateTime value
            = ldt.minus(Period.ofDays(10));

        // print result
        System.out.println("LocalDateTime after subtracting Days: "
                           + value);
    }
}
```

**Output:**

```java
Original LocalDateTime: 2019-12-31T19:15:30
LocalDateTime after subtracting Days: 2019-12-21T19:15:30

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html #减(java.time .时态. temporalamont)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#minus(java.time.temporal.TemporalAmount))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html #减(long，Java . time . temporalunit)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#minus(long, java.time.temporal.TemporalUnit))