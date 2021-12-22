# Java 中的 LocalDate plus()方法，示例

> 原文:[https://www . geesforgeks . org/local date-plus-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-plus-method-in-java-with-examples/)

在 LocalDate 类中，根据传递给它的参数，有两种类型的 plus()方法。

### 加(long amountToAdd，temporalunit unit)

**plus()** 一个 **LocalDate** 类的方法，用于返回该 LocalDate 的副本，并在 LocalDate 中添加指定数量的单位。如果无法添加金额，因为不支持该单位或其他原因，则会引发异常。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public LocalDate plus(long amountToAdd,
                      TemporalUnit unit)

```

**参数:**该方法接受两个参数:

*   **amountToAdd:** 是要添加到结果中的单位数量，可能为负数
*   **单位:**是要添加的量的单位。

**返回值:**此方法基于此日期时间返回**本地日期**，并添加指定的金额。

下面的程序说明了 plus()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalDate.plus() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate zonedlt
            = LocalDate.parse("2018-12-06");

        // add 300 Months to LocalDate
        LocalDate value
            = zonedlt.plus(300, ChronoUnit.MONTHS);

        // print result
        System.out.println("LocalDate after adding Months : "
                           + value);
    }
}
```

**Output:**

```
LocalDate after adding Months : 2043-12-06

```

### amounttoadd 临时挂载)

**plus()** 一个 **LocalDate** 类的方法，用于返回该 LocalDate 的副本，其中添加了指定数量的 LocalDate。该金额通常为“期间”或“持续时间”，但也可以是实现临时计费界面的任何其他类型。

**语法:**

```
public LocalDate plus(TemporalAmount amountToAdd)

```

**参数:**此方法只接受一个参数**金额加**即要加的金额，不应该为空。

**返回值:**此方法基于此日期时间返回**本地日期**，并进行加法运算。

下面的程序说明了 plus()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalDate.plus() method

import java.time.*;
public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate zonedlt
            = LocalDate.parse("2018-12-06");

        // add 100 Days to LocalDate
        LocalDate value
            = zonedlt.plus(Period.ofDays(100));

        // print result
        System.out.println("LocalDate after adding Days: "
                           + value);
    }
}
```

**Output:**

```
LocalDate after adding Days: 2019-03-16

```

**参考:**

*   [https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # plus(Java . time .时态. tempalamount)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#plus(java.time.temporal.TemporalAmount))
*   [https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # plus(long，Java . time . temporalunit)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#plus(long, java.time.temporal.TemporalUnit))