# Java 中的 HijrahChronology date()方法，示例:Set–1

> 原文:[https://www . geesforgeks . org/hijrah 年表-日期-方法-Java-带示例-set-1/](https://www.geeksforgeeks.org/hijrahchronology-date-method-in-java-with-example-set-1/)

**Java . time . chrono . Hijrah 年表**类的 **date()** 方法用于根据 Hijrah 日历系统获取给定年、月和日的本地日期。
**语法:**

```
public HijrahDate date(int prolepticYear,
                       int month,
                       int day)
```

**参数**:该方法以下列参数为参数。

*   **预测年:**回历年字段的整数预测年
*   **月:**HijrahDate 月字段的整数月
*   **日:**HijRahDate 日字段的整数日

**返回值:**该方法根据回历系统返回给定年、月、日的本地日期。
**异常:**如果给定的日、月、年字段无法形成结构化日期，该方法抛出 **DateTimeException** 。
以下举例说明**日期()**方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
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
            // creating and initializing  HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology used in HijrahDate
            HijrahChronology crono = hidate.getChronology();

            // getting HijrahDate for the
            // given date, month and year field
            // by using date() method
            HijrahDate date = crono.date(1440, 05, 24);

            // display the result
            System.out.println("HijrahDate is: " + date);
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

```
HijrahDate is: Hijrah-umalqura AH 1440-05-24
```