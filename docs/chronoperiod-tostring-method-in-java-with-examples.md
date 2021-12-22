# Java 中的计时 toString()方法，示例

> 原文:[https://www . geesforgeks . org/chronoperiod-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronoperiod-tostring-method-in-java-with-examples/)

Java 中**计时周期接口**的 **toString()** 方法用来返回这个计时周期的字符串表示。

**语法:**

```
ChronoPeriod toString()
```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回这个的字符串表示

下面的程序说明了上面的方法:

**程序 1** :

```
// Java code to show the toString() function

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodClass {

    // Function to negate given periods
    static void printString(ChronoPeriod p1)
    {

        System.out.println(p1.toString());
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining period
        int year = 4;
        int months = 11;
        int days = 10;
        ChronoPeriod p1 = Period.of(year, months, days);

        printString(p1);
    }
}
```

**输出:**

```
P4Y11M10D

```

**程序二** :

```
// Java code to show the toString() function

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodClass {

    // Function to negate given periods
    static void printString(ChronoPeriod p1)
    {

        System.out.println(p1.toString());
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining period
        int year = -4;
        int months = -11;
        int days = -10;
        ChronoPeriod p1 = Period.of(year, months, days);

        printString(p1);
    }
}
```

**输出:**

```
P-4Y-11M-10D

```

**参考**:[https://docs . Oracle . com/javae/9/docs/API/Java/time/chrono/chronopodo . html # tostring】](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#toString--)