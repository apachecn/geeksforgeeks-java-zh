# Java 中的 Minguo 年表 dateYearDay(Era，int，int)方法，示例

> 原文:[https://www . geeksforgeeks . org/Minguo 年表-datyeardayera-int-int-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguochronology-dateyeardayera-int-int-method-in-java-with-example/)

**Java . time . chrono . Minguo 年表**类的 **dateYearDay()** 方法用于根据特定时代的民国日历检索民国日期。

**语法:**

```
public MinguoDate dateYearDay(
  Era era, int yearOfEra, int dayOfYear)

```

**参数**:该方法以下列参数为参数:

*   **时代:**哪个是类型时代的对象
*   **年:**是民国年字段的整数规划年
*   **日:**是 MinguoDate 的日字段的整数日

**返回值:**该方法根据特定年份和日期的民国日历返回**民国日期**。

**异常:**该方法抛出**日期时间异常**-如果给定的数据无法形成日期。

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
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now();

            // getting MinguoChronology
            // used in MinguoDate
            MinguoChronology crono
                = hidate.getChronology();

            // getting MinguoDate for the
            // given date and year field
            // by using dateYearDay() method
            MinguoDate date
                = crono.dateYearDay(
                    MinguoEra.ROC,
                    2018,
                    24);

            // display the result
            System.out.println(
                "MinguoDate is: "
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

```
MinguoDate is: Minguo ROC 2018-01-24

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
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now();

            // getting MinguoChronology
            // used in MinguoDate
            MinguoChronology crono
                = hidate.getChronology();

            // getting MinguoDate for the
            // given date and year field
            // by using dateYearDay() method
            MinguoDate date
                = crono.dateYearDay(
                    MinguoEra.ROC,
                    1800,
                    -24);

            // display the result
            System.out.println(
                "MinguoDate is: "
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

```
passed parameter can not form a date
Exception thrown:
 java.time.DateTimeException:
 Invalid value for DayOfYear
 (valid values 1 - 365/366): -24

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/Minguo 年表. html # date year day-Java . time . chrono . era-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#dateYearDay-java.time.chrono.Era-int-int-)