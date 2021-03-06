# Java 中的日文年表日期(int，int，int)方法，示例

> 原文:[https://www . geeksforgeeks . org/Japanese 年表-dateint-int-int-method-in-Java-with-example/](https://www.geeksforgeeks.org/japanesechronology-dateint-int-int-method-in-java-with-example/)

**Java . time . chrono . Japanese 年表**类的 **date()** 方法用于根据日本日历系统获取给定年、月和日的当地日期。
**语法:**

```java
public JapaneseDate date(int prolepticYear,
                         int month,
                         int dayOfMonth)
```

**参数**:该方法以下列参数为参数。

*   **普理年:**日本年份字段的整数普理年
*   **月:**日语月字段的整数月
*   **日:**日本人日字段的整数日

**返回值:**该方法根据日本日历系统返回给定年、月、日的日本日期。
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
            // JapaneseDate Object
            JapaneseDate lodate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in JapaneseDate
            JapaneseChronology crono
                = lodate.getChronology();

            // getting JapaneseDate for the
            // given date, month and year field
            // by using date() mehtod
            JapaneseDate date
                = crono.date(2018, 05, 24);

            // display the result
            System.out.println(
                "JapaneseDate is: "
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

**Output:** 

```java
JapaneseDate is: Japanese Heisei 30-05-24
```