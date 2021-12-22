# Java 中的 LocalTime 减()方法，示例

> 原文:[https://www . geesforgeks . org/local time-减去方法-in-java-with-examples/](https://www.geeksforgeeks.org/localtime-minus-method-in-java-with-examples/)

在 LocalTime 类中，根据传递给它的参数，有两种类型的减()方法。

### 减(长数量到子管道，临时单位)

**减()**一个 **LocalTime** 类的方法，用于返回这个 LocalTime 的一个副本，并减去指定数量的单位。如果由于不支持该单位或其他原因而无法减去该金额，则会引发异常。

**语法:**

```java
public LocalTime minus(long amountToSubtract,
                       TemporalUnit unit)

```

**参数:**该方法接受两个参数 **amountToSubtract** 可以为负数，也可以接受**单位**为要减去的量的单位，不为空。

**返回值:**该方法根据该本地时间减去指定的金额返回**本地时间**。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行减法运算
*   **不支持的 temporaltypexception**–如果不支持该设备
*   **算术异常**–如果出现数值溢出

下面的程序说明了减()方法:
**程序 1:**

```java
// Java program to demonstrate
// LocalTime.minus() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create an LocalTime object
        LocalTime lt
            = LocalTime.parse("19:34:50.63");

        // subtract 12 Hours to LocalTime
        LocalTime value
            = lt.minus(12, ChronoUnit.HOURS);

        // print result
        System.out.println("LocalTime after subtracting 12 Hours: "
                           + value);
    }
}
```

**Output:**

```java
LocalTime after subtracting 12 Hours: 07:34:50.630

```

### >减号(临时数量到小计)

**减()**一个 **LocalTime** 类的方法，用于返回该 LocalTime 的一个副本，其中指定的数量减去日期时间。该金额通常为“期间”或“持续时间”，但也可以是实现临时计费界面的任何其他类型。

**语法:**

```java
public LocalTime minus(TemporalAmount amountTosubtract)

```

**参数:**此方法接受一个单参数 **amountTosubtract** 为要减去的量，不应为空。

**返回值:**该方法基于该日期时间进行减法运算，返回**本地时间**，不为空。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行减法运算
*   **算术异常**–如果出现数值溢出

下面的程序说明了减()方法:
**程序 1:**

```java
// Java program to demonstrate
// LocalTime.minus() method

import java.time.*;
public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime lt
            = LocalTime.parse("19:34:50.63");

        // subtract 55 Minutes to LocalTime
        LocalTime value
            = lt.minus(Duration.ofMinutes(55));

        // print result
        System.out.println("LocalTime after minus 55 Minutes: "
                           + value);
    }
}
```

**Output:**

```java
LocalTime after minus 55 Minutes: 18:39:50.630

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html #减(java.time .时态. tempalamount)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#minus(java.time.temporal.TemporalAmount))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html #减(long，Java . time . temporalunit)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#minus(long, java.time.temporal.TemporalUnit))