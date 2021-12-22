# Java 中的 Minguo 年表 dateYearDay(int，int)方法，示例

> 原文:[https://www . geeksforgeeks . org/Minguo 年表-date year dayint-int-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguochronology-dateyeardayint-int-method-in-java-with-example/)

**Java . time . chrono . Minguo 年表**类的**Dateyeday()**方法用于根据特定年份和日期的 Minguo 日历检索本地日期。

**语法:**

```
public MinguoDate dateYearDay(int year,
                              int day)

```

**参数**:该方法以下列参数为参数:

*   **年:**是民国年字段的整数规划年
*   **日:**是 MinguoDate 的日字段的整数日

**返回值:**此方法根据特定年份和日期的伊斯兰民国日历返回**当地日期**。

**异常:**如果给定的日、月、年字段不能形成结构化的日期，该方法抛出**日期时间异常**。

以下是举例说明 **dateYearDay()** 方法的例子:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
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
            // creating and initializing MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

            // getting MinguoChronology used in MinguoDate
            MinguoChronology crono = hidate.getChronology();

            // getting MinguoDate for the
            // given date and year field
            // by using dateYearDay() method
            MinguoDate date = crono.dateYearDay(1440, 24);

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

```
MinguoDate is: Minguo ROC 1440-01-24

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
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
            // creating and initializing MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

            // getting MinguoChronology used in MinguoDate
            MinguoChronology crono = hidate.getChronology();

            // getting MinguoDate for the
            // given date and year field
            // by using dateYearDay() method
            MinguoDate date = crono.dateYearDay(2019, -24);

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

```
passed parameter can not form a date
Exception thrown:
 java.time.DateTimeException:
 Invalid value for DayOfYear
 (valid values 1 - 365/366): -24

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/Minguo 年表. html#dateYearDay-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#dateYearDay-int-int-)