# Java 中的计时获取年表()方法，示例

> 原文:[https://www . geeksforgeeks . org/chrono period-get timer-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronoperiod-getchronology-method-in-java-with-examples/)

用 Java 中**计时周期界面**的**get 年表()方法**得到这个周期的年表，就是 ISO 日历系统。

**语法:**

```
ChronoPeriod getChronology()
```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回这个的字符串表示

下面的程序说明了上面的方法:

**程序 1** :

```
// Java code to show the getChronology() function

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodClass {

    // Function to negate given periods
    static void printChronology(ChronoPeriod p1)
    {

        System.out.println(p1.getChronology());
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining period
        int year = 4;
        int months = 11;
        int days = 10;
        ChronoPeriod p1 = Period.of(year, months, days);

        printChronology(p1);
    }
}
```

**输出:**

```
ISO

```

**程序二** :

```
// Java code to show the getChronology() function

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodClass {

    // Function to negate given periods
    static void printChronology(ChronoPeriod p1)
    {

        System.out.println(p1.getChronology());
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining period
        int year = -4;
        int months = -11;
        int days = -10;
        ChronoPeriod p1 = Period.of(year, months, days);

        printChronology(p1);
    }
}
```

**输出:**

```
ISO

```

**参考**:[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronoperiod . html # GetError–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#getChronology--)