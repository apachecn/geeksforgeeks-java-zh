# Java 中的等时日期(int，int，int)方法，示例

> 原文:[https://www . geesforgeks . org/isochronomics-dateint-int-int-method-in-Java-with-example/](https://www.geeksforgeeks.org/isochronology-dateint-int-int-method-in-java-with-example/)

**Java . time . chrono . isochronology**类的 **date()** 方法用于根据 ISO 日历系统获取给定年、月和日的本地日期。

**语法:**

```java
public LocalDate date(int prolepticYear,
                      int month,
                      int dayOfMonth)
```

**参数**:该方法以下列参数为参数。

*   **预测年:**国际标准化组织年份字段的整数预测年
*   **月:**ISO 月字段的整数月
*   **日:**ISO 日字段的整数日

**返回值:**该方法根据 Iso 日历系统返回给定年、月、日的本地日期。
**异常:**如果给定的日、月、年字段无法形成结构化日期，该方法抛出 **DateTimeException** 。
以下举例说明**日期()**方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// date() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing LocalDate Object
            LocalDate lodate = LocalDate.now();

            // getting IsoChronology used in LocalDate
            IsoChronology crono = lodate.getChronology();

            // getting LocalDate for the
            // given date, month and year field
            // by using date() method
            LocalDate date = crono.date(1440, 05, 24);

            // display the result
            System.out.println("LocalDate is: " + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can "
                               + "not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:** 

```java
LocalDate is: 1440-05-24
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// date() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing LocalDate Object
            LocalDate lodate = LocalDate.now();

            // getting IsoChronology used in LocalDate
            IsoChronology crono = lodate.getChronology();

            // getting LocalDate for the
            // given date, month and year field
            // by using date() method
            LocalDate date = crono.date(2020, 05, 34);

            // display the result
            System.out.println("LocalDate is: " + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can "
                               + "not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output**

```java
passed parameter can not form a date
Exception thrown: java.time.DateTimeException: Invalid value for DayOfMonth (valid values 1 - 28/31): 34

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/isochronomics . html # date-int-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#date-int-int-int-)