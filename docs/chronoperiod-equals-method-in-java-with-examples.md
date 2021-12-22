# Java 中的计时周期等于()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronoperiod-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronoperiod-equals-method-in-java-with-examples/)

Java 中**计时周期界面**的**等于()**方法用于检查两个给定周期是否相等。

这种比较是基于计时周期类型以及三年、三个月和三个日期中的每一个。要相等，所有三年、月和日期必须各自相等。

**语法:**

```
boolean equals(ChronoPeriod secondChronoPeriod)
```

**参数:**此方法接受单个参数*秒时周期*，这是另一个要比较的周期。

**返回值:**如果给定周期相等，上述方法返回真，否则返回假。

下面的程序说明了上述方法:

**程序 1:**

```
// Java code to show the period
// equals for two given periods

import java.time.*;
import java.time.chrono.*;

public class ChronoPeriodClass {

    // Function to check if two given periods
    // are equals or not
    static boolean
    checkIfEqualChronoPeriod(ChronoPeriod firstChronoPeriod,
                             ChronoPeriod secondChronoPeriod)
    {

        return firstChronoPeriod.equals(secondChronoPeriod);
    }

    // Driver Code
    public static void main(String[] args)
    {

        // Given period
        ChronoPeriod first = Period.ofDays(28);
        ChronoPeriod second = Period.ofDays(8);

        System.out.println(
            checkIfEqualChronoPeriod(first, second));
    }
}
```

**输出:**

```
false

```

**程序二:**

```
// Java code to show the period
// equals for two given periods

import java.time.*;
import java.time.chrono.*;

public class ChronoPeriodClass {

    // Function to check if two given periods
    // are equals or not
    static boolean
    checkIfEqualChronoPeriod(ChronoPeriod firstChronoPeriod,
                             ChronoPeriod secondChronoPeriod)
    {

        return firstChronoPeriod.equals(secondChronoPeriod);
    }

    // Driver Code
    public static void main(String[] args)
    {

        // Given period
        ChronoPeriod first2 = Period.ofDays(28);
        ChronoPeriod second2 = Period.ofDays(28);

        System.out.println(
            checkIfEqualChronoPeriod(first2, second2));
    }
}
```

**输出:**

```
true

```

**参考**:[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronoperiod . html # equals-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#equals-java.lang.Object-)