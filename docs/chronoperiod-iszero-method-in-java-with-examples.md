# 计时周期为零()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/chronoperiod-is zero-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronoperiod-iszero-method-in-java-with-examples/)

Java 中**计时周期类**的**是零()方法**用来检查这个周期中的三个 YEAR、MONTH、DAYS 是否都是零。

为了检查零周期，这个函数被广泛使用。零周期是指三个年份、月份和天数都为零的周期。

**语法:**

```
boolean isZero()
```

**参数:**该方法不接受任何参数。

**返回值:**如果给定期间的三个值 YEARS、MONTHS、DAYS 都为零，则该方法返回布尔值 True，否则返回 False。

下面的程序说明了上述方法:

**程序 1** :

```
// Java code to show the function isZero()
// to check whether all of the three given units
// YEAR, MONTH, DAY are zero.

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodDemo {

    // Function to check if all
    // of the three YEAR, MONTH, DAY are zero
    static void ifZero(int year, int months, int days)
    {
        ChronoPeriod period = Period.of(year, months, days);
        System.out.println(period.isZero());
    }

    // Driver Code
    public static void main(String[] args)
    {

        int year = 0;
        int months = 0;
        int days = 0;

        ifZero(year, months, days);
    }
}
```

**输出:**

```
true

```

**程序二** :

```
// Java code to show the function isZero()
// to check whether all of the three given units
// YEAR, MONTH, DAY are zero.

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodDemo {

    // Function to check if all
    // of the three YEAR, MONTH, DAY are zero
    static void ifZero(int year, int months, int days)
    {
        ChronoPeriod period = Period.of(year, months, days);
        System.out.println(period.isZero());
    }

    // Driver Code
    public static void main(String[] args)
    {

        int year = 0;
        int months = 0;
        int days = -12;

        ifZero(year, months, days);
    }
}
```

**输出:**

```
false

```

**参考**:[https://docs . Oracle . com/javae/9/docs/API/Java/time/chrono/chronopodo . html # ice ero】](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#isZero--)