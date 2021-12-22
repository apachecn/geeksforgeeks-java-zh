# Java 中的计时加()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronoperiod-plus-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronoperiod-plus-method-in-java-with-examples/)

Java 中**计时周期界面**的 **plus()** 方法是将给定的周期量加到指定的周期上。该功能在年、月和日分别运行。

**注意:**不进行归一化。12 个月和 1 年是不同的。

**语法:**

```java
ChronoPeriod plus(TemporalAmount amountToAdd)
```

**参数:**此功能接受单个参数*金额添加*，即**金额**添加至期间。它不能为空。

**返回值**该函数返回一个基于给定周期的计时周期，加上请求的周期，该值不能为空。

**例外:**

*   **Date and time exception** : If the specified amount has a non-ISO chronology or contains invalid units, this exception will be returned.
*   **Arithmetic exception** : If there is a numerical overflow, catch the exception.

下面的程序说明了上述方法:

**程序 1** :

```java
// Java code to show the function plus()
// to subtract the two given periods

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodDemo {

    // Function to subtract two given periods
    static void addChronoPeriod(ChronoPeriod p1, ChronoPeriod p2)
    {

        System.out.println(p1.plus(p2));
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining first period
        int year = 4;
        int months = 11;
        int days = 10;
        ChronoPeriod p1 = Period.of(year, months, days);

        // Defining second period
        int year1 = 2;
        int months1 = 7;
        int days1 = 8;
        ChronoPeriod p2 = Period.of(year1, months1, days1);

        addChronoPeriod(p1, p2);
    }
}
```

**输出:**

```java
P6Y18M18D

```

**程序 2** :计时周期可以是负数。

```java
// Java code to show the function plus()
// to subtract the two given periods

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodDemo {

    // Function to add two given periods
    static void addChronoPeriod(ChronoPeriod p1, ChronoPeriod p2)
    {

        System.out.println(p1.plus(p2));
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining second period
        int year1 = 2;
        int months1 = 7;
        int days1 = 8;
        ChronoPeriod p1 = Period.of(year1, months1, days1);

        // Defining first period
        int year = 4;
        int months = 11;
        int days = 10;
        ChronoPeriod p2 = Period.of(year, months, days);

        addChronoPeriod(p1, p2);
    }
}
```

**输出:**

```java
P6Y18M18D

```

**参考**:[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronoperiod . html # plus-Java . time . temporal mount-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#plus-java.time.temporal.TemporalAmount-)