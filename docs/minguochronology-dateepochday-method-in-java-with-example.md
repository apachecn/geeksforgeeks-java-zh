# Java 中的 minuo 年表 dateEpochDay()方法，示例

> 原文:[https://www . geeksforgeeks . org/minguoberythro-datepochday-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguochronology-dateepochday-method-in-java-with-example/)

**Java . time . chrono . Minguo 年表**类的 **dateEpochDay()** 方法用于从大纪元日开始，根据 Minguo 日历系统获取当地日期。
**语法:**

```
public MinguoDate dateEpochDay(long epochDay)
```

**参数**:该方法以 long 类型的 **epochDay** 为参数。
**返回值:**此方法从大纪元日开始根据民国历法系统返回当地日期。
**异常:**如果给定的纪元日无法形成结构化日期，则该方法抛出**日期时间异常**。
以下是举例说明**datepochday()**方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// Minguo() method

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

            // display the result
            System.out.println("current MinguoDate is: "
                               + hidate);

            // getting MinguoDate for the
            // given TemporalAccessor object
            // by using date() method
            hidate = crono.dateEpochDay(23456);

            // display the result
            System.out.println("\nMinguoDate(according "
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
current MinguoDate is: Minguo ROC 110-06-22

MinguoDate(according to ephochday) is: Minguo ROC 123-03-22

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// Minguo() method

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

            // display the result
            System.out.println("current MinguoDate is: "
                               + hidate);

            // getting MinguoDate for the
            // given TemporalAccessor object
            // by using date() method
            hidate = crono.dateEpochDay(234568);

            // display the result
            System.out.println("\nMinguoDate(according "
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
current MinguoDate is: Minguo ROC 110-06-22

MinguoDate(according to ephochday) is: Minguo ROC 701-03-24

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/Minguo 年表. html # datepochday-long-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#dateEpochDay-long-)