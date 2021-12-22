# Java 中的 ChronoPeriod get()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronoperiod-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronoperiod-get-method-in-java-with-examples/)

Java 中**计时周期界面**的 **get()** 方法用于从该计时周期中获取参数中给出的请求单位(年、月或日)的值。

**语法:**

```
long get(TemporalUnit unit)
```

**参数:**该方法接受一个类型为临时单位的单参数*单位*，该单位是获得所需单位的单位。

**返回值:**该函数返回请求单位的长值。

**异常:**

*   **Date and time exception** –If the unit in the parameter is not supported, this method will throw a date and time exception.
*   不受支持的 dtime type exception 喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂喂，云娥 unsupportedtmporaltypeexception。

下面的程序说明了上述方法:

**程序 1:**

```
// Java code to show the function get()
// which gives the requested unit

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodDemo {

    // Function to get requested unit
    static void getUnit(int year, int months, int days)
    {
        ChronoPeriod period = Period.of(year, months, days);
        System.out.println(period.get(ChronoUnit.DAYS));
    }

    // Driver Code
    public static void main(String[] args)
    {

        int year = 8;
        int months = 5;
        int days = 25;

        getUnit(year, months, days);
    }
}
```

**输出:**

```
25

```

**程序二:**

```
// Java code to show the function get()
// which gives the requested unit

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodDemo {

    // Function to get requested unit
    static void getUnit(int year, int months, int days)
    {
        ChronoPeriod period = Period.of(year, months, days);
        System.out.println(period.get(ChronoUnit.YEARS));
    }

    // Driver Code
    public static void main(String[] args)
    {

        int year = 11;
        int months = 3;
        int days = 21;

        getUnit(year, months, days);
    }
}
```

**输出:**

```
11

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronoperiod . html # get-Java . time . temporal unit-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoChronoPeriod.html#get-java.time.temporal.TemporalUnit-)