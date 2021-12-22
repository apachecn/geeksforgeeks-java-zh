# Java 中的 hijrah 年表 dateYearDay()方法，示例:第 2 集

> 原文:[https://www . geesforgeks . org/hijrah 年表-date year day-Java 中的方法-带示例-set-2/](https://www.geeksforgeeks.org/hijrahchronology-dateyearday-method-in-java-with-example-set-2/)

**Java . time . chrono . hijrah 年表**类的**Dateyeday()**方法用于根据特定时代的伊斯兰回历检索当地日期。

**语法:**

```java
public HijrahDate dateYearDay(Era era,
                              int year,
                              int day)
```

**参数**:该方法以下列参数为参数。

*   **Era:** is the type era.
*   **year of the object:** is the date of Hijra.
*   **date:** is the date of Hijra.

日字段的整数日

**返回值:**该方法根据特定时代的伊斯兰回历返回**当地日期**。

**异常:**如果给定的日、月、年字段不能形成结构化的日期，该方法抛出**日期时间异常**。

以下是举例说明 **dateYearDay()** 方法的例子:

**例 1:**

```java
// Java program to demonstrate
// dateYearDay() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology
            // used in HijrahDate
            HijrahChronology crono
                = hidate.getChronology();

            // getting HijrahDate for the
            // given date and year field
            // by using dateYearDay() method
            HijrahDate date
                = crono.dateYearDay(
                    HijrahEra.AH, 1440, 24);

            // display the result
            System.out.println("HijrahDate is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can "
                               + "not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
HijrahDate is: Hijrah-umalqura AH 1440-01-24

```

**例 2:**

```java
// Java program to demonstrate
// dateYearDay() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.now();

            // getting HijrahChronology
            // used in HijrahDate
            HijrahChronology crono
                = hidate.getChronology();

            // getting HijrahDate for the
            // given date and year field
            // by using dateYearDay() method
            HijrahDate date
                = crono.dateYearDay(
                    HijrahEra.AH, 2019, 24);

            // display the result
            System.out.println("HijrahDate is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can "
                               + "not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
passed parameter can not form a date
Exception thrown: java.time.DateTimeException: Invalid Hijrah date, year: 2019, month: 1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/hijrah 年表. html # date year day-Java . time . chrono . era-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#dateYearDay-java.time.chrono.Era-int-int-)