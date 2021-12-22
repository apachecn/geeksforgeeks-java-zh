# Java 中的 LocalDate 减()方法，带示例

> 原文:[https://www . geesforgeks . org/local date-减去方法-in-java-with-examples/](https://www.geeksforgeeks.org/localdate-minus-method-in-java-with-examples/)

在 LocalDate 类中，根据传递给它的参数，有两种类型的减()方法。

### 减(长量到子体积，时间单位)

**减()**方法的一个 **LocalDate** 类用于返回该 LocalDate 的一个副本，其中指定数量的单位减去 LocalDate。如果由于不支持该单位或其他原因而无法减去该金额，则会引发异常。

**语法:**

```
public LocalDate minus(long amountToSubtract,
                       TemporalUnit unit)

```

**参数:**该方法接受两个参数:

*   **amountToSubtract:** 是要从结果中减去的单位的数量，可以是负数
*   **单位:**是要减去的量的单位。

**返回值:**该方法根据该日期时间减去指定的金额返回**本地日期**。

**异常:**该方法抛出以下异常:

*   **日期时间异常**:如果不能做减法
*   **unsupportedtemporaltypexception**:如果不支持该单元
*   **算术异常**:如果出现数值溢出

下面的程序说明了减()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalDate.minus() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate zonedlt
            = LocalDate.parse("2018-12-06");

        // subtract 12 Years to LocalDate
        LocalDate value
            = zonedlt.minus(12, ChronoUnit.YEARS);

        // print result
        System.out.println("LocalDate after "
                           + "subtracting Months: "
                           + value);
    }
}
```

**Output:**

```
LocalDate after subtracting Months: 2006-12-06

```

### 减(临时金额到小计)

**减()**方法的一个 **LocalDate** 类用来返回这个 LocalDate 的一个副本，指定的数量减去 LocalDate。该金额通常为“期间”或“持续时间”，但也可以是实现临时计费界面的任何其他类型。

**语法:**

```
public LocalDate minus(TemporalAmount amountTosubtract)

```

**参数:**此方法接受一个单参数 **amountTosubtract** 为要减去的量，不应为空。

**返回值:**该方法基于该日期时间进行减法运算，返回**本地日期**，不为空。

**异常:**该方法抛出以下异常:

*   **日期时间异常:**如果不能做减法
*   **算术异常:**如果出现数值溢出

下面的程序说明了减()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalDate.minus() method

import java.time.*;
public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate zonedlt
            = LocalDate.parse("2018-12-06");

        // subtract 30 Days to LocalDate
        LocalDate value
            = zonedlt.minus(Period.ofDays(30));

        // print result
        System.out.println("LocalDate after"
                           + " subtracting Days: "
                           + value);
    }
}
```

**Output:**

```
LocalDate after subtracting Days: 2018-11-06

```

**参考:**

*   [https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html #减(Java . time . temporal mount)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#minus(java.time.temporal.TemporalAmount))
*   [https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html #减(long，Java . time . temporalunit)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#minus(long, java.time.temporal.TemporalUnit))