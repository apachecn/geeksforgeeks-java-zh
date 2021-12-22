# Java 中带有 DayOfMonth()方法的 LocalDate，示例

> 原文:[https://www . geeksforgeeks . org/local date-with dayofmonth-in-Java-method-with-examples/](https://www.geeksforgeeks.org/localdate-withdayofmonth-method-in-java-with-examples/)

Java 中 **LocalDate 类**的 **withDayOfMonth()** 方法返回一个更改了月日的 LocalDate 的副本。

**语法:**

```java
public LocalDate withDayOfMonth(int dayOfMonth)
```

**参数:**该方法接受一个强制参数**日期**，在结果中设置一个月中的哪一天，从 1 到 28-31。

**返回:**该函数根据请求日期返回一个本地日期，不为空。

**异常**:当月日值无效时，函数抛出**日期时间异常**。

下面的程序说明了**local date . witdayofmonth()**方法:

**程序 1:**

```java
// Program to illustrate the withDayOfMonth() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Parses the date
        LocalDate dt1 = LocalDate.parse("2018-12-07");
        LocalDate result = dt1.withDayOfMonth(01);

        // Prints the date with year
        System.out.println("The date with day of the month is: " + result);
    }
}
```

**输出:**

```java
The date with day of the month is: 2018-12-01

```

**程序二:**

```java
// Program to illustrate the withDayOfMonth() method
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
            LocalDate result = dt1.withDayOfMonth(35);

            // Prints the date with year
            System.out.println("The date with day of the month is: " + result);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.time.DateTimeException: Invalid value for DayOfMonth (valid values 1 - 28/31): 35

```

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # with dayofmonth(int)