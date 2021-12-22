# Java 中的 Japanese 年表 dateEpochDay()方法，示例

> 原文:[https://www . geeksforgeeks . org/Japanese 年表-date epochday-Java 中的方法-带示例/](https://www.geeksforgeeks.org/japanesechronology-dateepochday-method-in-java-with-example/)

**Java . time . chrono . Japanese 年表**类的 **dateEpochDay()** 方法用于根据日本日历系统从大纪元日获取日本日期。
**语法:**

```
public JapaneseDate dateEpochDay(long epochDay)
```

**参数**:该方法以 long 类型的 epochDay 为参数。
**返回值:**该方法从另一个 TemporalAccessor 对象返回根据日本日历系统的本地日期。
**异常:**如果该纪元日无法创建日本日期，此方法抛出**日期时间异常**。
以下是举例说明**datepochday()**方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// dateEpochDay() method

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
            JapaneseDate hidate = JapaneseDate.now();

            // getting JapaneseChronology
            // used in JapaneseDate
            JapaneseChronology crono
                = hidate.getChronology();

            // display the result
            System.out.println("current JapaneseDate is: "
                               + hidate);

            // getting JapaneseDate for the
            // given TemporalAccessor object
            // by using date() method
            hidate = crono.dateEpochDay(23456);

            // display the result
            System.out.println("\nJapaneseDate(according "
                               + "to ephochday) is: "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output**

```
current JapaneseDate is: Japanese Reiwa 3-06-22

JapaneseDate(according to ephochday) is: Japanese Reiwa 16-03-22

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// dateEpochDay() method

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
            JapaneseDate hidate = JapaneseDate.now();

            // getting JapaneseChronology
            // used in JapaneseDate
            JapaneseChronology crono
                = hidate.getChronology();

            // display the result
            System.out.println("current JapaneseDate is: "
                               + hidate);

            // getting JapaneseDate for the
            // given TemporalAccessor object
            // by using date() method
            hidate = crono.dateEpochDay(-999999999);

            // display the result
            System.out.println("\nJapaneseDate(accoding "
                               + "to ephochday) is: "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:** 

```
current JapaneseDate is: Japanese Heisei 32-04-13
passed parameter can not form a date
Exception thrown: java.time.DateTimeException: JapaneseDate before Meiji 6 is not supported
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/Japanese seriogram . html # dateepchtday-long-T4】