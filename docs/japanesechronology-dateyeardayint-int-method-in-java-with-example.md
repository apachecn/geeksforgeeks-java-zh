# Java 中的日本纪年法 dateYearDay(int，int)方法，示例

> 原文:[https://www . geesforgeks . org/Japanese 年表-date year dayint-int-method-in-Java-with-example/](https://www.geeksforgeeks.org/japanesechronology-dateyeardayint-int-method-in-java-with-example/)

**Java . time . chrono . Japanese 年表**类的 **dateYearDay()** 方法用于根据特定年份和日期的 Iso 日历检索日语日期。

**语法:**

```java
public JapaneseDate dateYearDay(
  int prolepticYear, int dayOfYear)

```

**参数**:该方法以下列参数为参数:

*   **年:**是日本日期年字段的整数优先年
*   **日:**是日本日期的日字段的整数日

**返回值:**此方法根据特定年份和日期的日本日历返回**日本日期**。

**异常:**该方法抛出**日期时间异常**-如果给定的数据无法形成日期。

以下是举例说明 **dateYearDay()** 方法的例子:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

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
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in JapaneseDate
            JapaneseChronology crono
                = hidate.getChronology();

            // getting JapaneseDate for the
            // given date and year field
            // by using dateYearDay() method
            JapaneseDate date
                = crono.dateYearDay(2018, 24);

            // display the result
            System.out.println(
                "JapaneseDate is: "
                + date);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can "
                + "not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**Output:**

```java
JapaneseDate is: Japanese Heisei 30-01-24

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

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
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in JapaneseDate
            JapaneseChronology crono
                = hidate.getChronology();

            // getting JapaneseDate for the
            // given date and year field
            // by using dateYearDay() method
            JapaneseDate date
                = crono.dateYearDay(1440, 24);

            // display the result
            System.out.println(
                "JapaneseDate is: "
                + date);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can "
                + "not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**Output:**

```java
passed parameter can not form a date
Exception thrown:
 java.time.DateTimeException:
 JapaneseDate before Meiji 6 is not supported

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/Japanese seriogram . html # date year day-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#dateYearDay-int-int-)