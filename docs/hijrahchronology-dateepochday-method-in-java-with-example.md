# Java 中的 HijrahChronology dateEpochDay()方法，示例

> 原文:[https://www . geeksforgeeks . org/hijrah 年表-datepochday-method-in-Java-with-example/](https://www.geeksforgeeks.org/hijrahchronology-dateepochday-method-in-java-with-example/)

**Java . time . chrono . Hijrah 年表**类的 **dateEpochDay()** 方法用于从大纪元日根据 Hijrah 日历系统获取本地日期。
**语法:**

```
public HijrahDate dateEpochDay(long epochDay)
```

**参数**:该方法以 long 类型的 epochDay 为参数。
**返回值:**该方法从另一个 TemporalAccessor 对象返回根据 Hijrah 日历系统的本地日期。
**异常:**如果给定的纪元日无法形成结构化日期，该方法抛出**日期时间异常**。
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
            // creating and initializing  HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology used in HijrahDate
            HijrahChronology crono = hidate.getChronology();

            // display the result
            System.out.println("current HijrahDate is: "
                               + hidate);

            // getting HijrahDate for the
            // given TemporalAccessor object
            // by using date() method
            hidate = crono.dateEpochDay(23456);

            // display the result
            System.out.println("\nHijrahDate(according "
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
current HijrahDate is: Hijrah-umalqura AH 1442-11-15

HijrahDate(according to ephochday) is: Hijrah-umalqura AH 1456-01-01

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
            // creating and initializing  HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology used in HijrahDate
            HijrahChronology crono = hidate.getChronology();

            // display the result
            System.out.println("current HijrahDate is: "
                               + hidate);

            // getting HijrahDate for the
            // given TemporalAccessor object
            // by using date() method
            hidate = crono.dateEpochDay(234568);

            // display the result
            System.out.println("HijrahDate(according "
                               + "to ephochday) is: "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println("\npassed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output**

```
current HijrahDate is: Hijrah-umalqura AH 1442-11-15

passed parameter can not form a date
Exception thrown: java.time.DateTimeException: Hijrah date out of range

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/hijrah 年表. html # datepochday-long-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#dateEpochDay-long-)