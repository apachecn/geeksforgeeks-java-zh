# Java 中的计时 getUnits()方法，示例

> 原文:[https://www . geesforgeks . org/chronoperiod-get units-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronoperiod-getunits-method-in-java-with-examples/)

Java 中**计时周期类**的 **getUnits()方法**用来获取该计时周期支持的单位集。支持的单位是列表中的年、月、日(仅按此顺序)。

**语法:**

```
List getUnits()
```

**参数:**该方法不接受任何参数。

**返回值**该方法返回包含年、月、日的列表。

下面的程序说明了上述方法:

**程序 1** :

```
// Java code to show the function getUnits()
// to get the set of units supported by period

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodDemo {

    // Function to get the set of units supported by period
    static void getNumberOfDays(int year, int months, int days)
    {
        ChronoPeriod period = Period.of(year, months, days);
        System.out.println(period.getUnits());
    }

    // Driver Code
    public static void main(String[] args)
    {
        int year = 1;
        int months = 13;
        int days = 36;

        getNumberOfDays(year, months, days);
    }
}
```

**输出:**

```
[Years, Months, Days]

```

**程序二** :

```
// Java code to show the function getUnits()
// to get the set of units supported by period

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodDemo {

    // Function to get the set of units supported by period
    static void getNumberOfDays(int year, int months, int days)
    {
        ChronoPeriod period = Period.ofDays(days);
        System.out.println(period.getUnits());
    }

    // Driver Code
    public static void main(String[] args)
    {
        int year = 0;
        int months = 0;
        int days = 0;

        getNumberOfDays(year, months, days);
    }
}
```

**输出:**

```
[Years, Months, Days]

```

**参考**:[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronoperiod . html # getUnits–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#getUnits--)