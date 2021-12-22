# Java 中的 Minguo 年表日期(int，int，int)方法，示例

> 原文:[https://www . geeksforgeeks . org/minguoberogram-dateint-int-int-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguochronology-dateint-int-int-method-in-java-with-example/)

**Java . time . chrono . Minguo 年表**类的 **date()** 方法用于根据给定年、月、日的 Minguo 日历系统获取当地日期。
**语法:**

```java
public MinguoDate date(int prolepticYear,
                       int month,
                       int dayOfMonth)
```

**参数**:该方法以下列参数为参数。

*   **预测年:**明国日期年份字段的整数预测年
*   **月:**mingodate 月字段的整数月
*   **日:**日字段为 MinguoDate 的整数日

**返回值:**该方法根据民国历法系统返回给定年、月、日的当地日期。
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
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

            // getting MinguoChronology
            // used in MinguoDate
            MinguoChronology crono
                = hidate.getChronology();

            // getting MinguoDate for the
            // given date, month and year field
            // by using date() mehtod
            MinguoDate date = crono.date(2040, 05, 24);

            // display the result
            System.out.println("MinguoDate is: " + date);
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
MinguoDate is: Minguo ROC 2040-05-24
```