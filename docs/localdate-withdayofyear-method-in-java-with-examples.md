# Java 中带有 DayOfYear()方法的 LocalDate 示例

> 原文:[https://www . geesforgeks . org/local date-with dayof year-in-Java-method-with-examples/](https://www.geeksforgeeks.org/localdate-withdayofyear-method-in-java-with-examples/)

Java 中 **LocalDate 类**的 **withDayOfYear()** 方法返回一个该 LocalDate 的副本，其中更改了日期。

**语法:**

```
public LocalDate withDayOfYear(int dayOfYear)
```

**参数:**该方法接受一个强制参数**dayfyear**，指定在结果中设置的日期，从 1 到 365-366。

**返回:**该函数根据请求日期返回一个本地日期，不为空。

**异常**:当日数值无效时，函数抛出**日期时间异常**。

以下程序说明了**local date . witdayofyear()**方法:

**程序 1:**

```
// Program to illustrate the withDayOfYear() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Parses the date
        LocalDate dt1 = LocalDate.parse("2018-12-07");
        LocalDate result = dt1.withDayOfYear(01);

        // Prints the date with year
        System.out.println("The date with day of year is: " + result);
    }
}
```

**输出:**

```
The date with day of year is: 2018-01-01

```

**程序二:**

```
// Program to illustrate the withDayOfYear() method
// Exceptions
import java.util.*;
import java.time.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {

        try {
            // Parses the date
            LocalDate dt1 = LocalDate.parse("2018-12-07");
            LocalDate result = dt1.withDayOfYear(370);

            // Prints the date with year
            System.out.println("The date with month is: " + result);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
java.time.DateTimeException: Invalid value for DayOfYear (valid values 1 - 365/366): 370

```

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # with dayofyear(int)