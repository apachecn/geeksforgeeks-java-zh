# Java 中的 LocalDate ofYearDay()方法，带示例

> 原文:[https://www . geesforgeks . org/local date-of yeyay-in-Java-method-with-examples/](https://www.geeksforgeeks.org/localdate-ofyearday-method-in-java-with-examples/)

Java 中 **LocalDate** 类的**year(int year，int dayOfYear)** 方法用于从输入的年份和日期中获取 **LocalDate** 的实例。这里不传递月份值。过去的年份构成了实例的年份，日和月是根据日期计算的。在这里，1 月 1 日是开始的日子。因此，如果 dayOfYear 被作为 32 通过，这意味着前 31 天形成 1 月，第 32 天是 2 月 1 日。

**语法:**

```
public static LocalDate
          ofYearDay(int year, 
                    int dayOfYear)

```

**参数:**该方法接受两个参数:

*   **年**–整数型，代表年份。它从最小年到最大年不等。
*   **dayOfYear**–整数类型，代表一年中的某一天。从 1 到 366 不等。

**返回值:**此方法返回**本地日期**。

**异常:**如果任何字段的值超出范围或一年中的某一天无效，此方法将抛出**日期时间异常**。

下面的程序说明了 Java 中的 year(年内，日内)方法:

**程序 1:**

```
// Java program to demonstrate
// LocalDate.ofYearDay(int year,
// int dayOfYear) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDate object
        LocalDate localdate
            = LocalDate.ofYearDay(
                2020, 134);

        // print full date
        System.out.println("Date: "
                           + localdate);
    }
}
```

**Output:**

```
Date: 2020-05-13

```

**程序 2:**

```
// Java program to demonstrate
// LocalDate.ofYearDay(int year,
int dayOfYear) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDate object
        LocalDate localdate
            = LocalDate.ofYearDay(
                2020, 134);

        // print month
        System.out.println(
            "Month: "
            + localdate.getMonth());
    }
}
```

**Output:**

```
Month: MAY

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # of yeyay(int，int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#ofYearDay(int, int))