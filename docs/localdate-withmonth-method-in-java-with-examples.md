# Java 中的 LocalDate withMonth()方法，示例

> 原文:[https://www . geesforgeks . org/local date-with month-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-withmonth-method-in-java-with-examples/)

Java 中 **LocalDate 类**的 **withMonth()** 方法返回该 LocalDate 的一个副本，其中更改了月份。

**语法:**

```java
public LocalDate withMonth(int month)
```

**参数:**该方法接受一个强制参数**月**，指定在结果中设置的月份，从 1 月 1 日到 12 月 12 日。

**返回:**该函数返回基于该日期的本地日期和请求的月份，不为空。

**异常**:当年月值无效时，函数抛出**日期时间异常**。

下面的程序说明了 **LocalDate.withMonth()** 方法:

**程序 1:**

```java
// Program to illustrate the withMonth() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Parses the date
        LocalDate dt1 = LocalDate.parse("2018-12-07");
        LocalDate result = dt1.withMonth(01);

        // Prints the date with year
        System.out.println("The date with month is: " + result);
    }
}
```

**输出:**

```java
The date with month is: 2018-01-07

```

**程序二:**

```java
// Program to illustrate the withMonth() method
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
            LocalDate result = dt1.withMonth(13);

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

```java
java.time.DateTimeException: Invalid value for MonthOfYear (valid values 1 - 12): 13

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # with month(int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#withMonth(int))