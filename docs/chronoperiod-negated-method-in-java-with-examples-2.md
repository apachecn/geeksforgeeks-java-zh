# Java 中的计时周期求反()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronoperiod-invalid-method-in-Java-with-examples-2/](https://www.geeksforgeeks.org/chronoperiod-negated-method-in-java-with-examples-2/)

Java 中**计时周期接口**的**求反()**方法是在否定了 YEAR、MONTH、DAY 周期的所有元素后，返回一个计时周期的新实例。

**语法:**

```java
ChronoPeriod negated()
```

**参数:**该方法不接受任何参数。

**返回值:**这个方法在否定了周期的每个元素后，返回一个 ChronoPeriod 的新实例。

**异常:**它抛出一个**算术异常**。如果发生数字溢出，将捕获此异常。

下面的程序说明了上面的方法:

**程序 1** :

```java
// Java code to show the function to negate all
// elements of the period

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodClass {

    // Function to negate given periods
    static void toNegate(ChronoPeriod p1)
    {

        System.out.println(p1.negated());
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining period
        int year = 4;
        int months = 11;
        int days = 10;
        ChronoPeriod p1 = Period.of(year, months, days);

        toNegate(p1);
    }
}
```

**输出:**

```java
P-4Y-11M-10D

```

**程序二** :

```java
// Java code to show the function to negate all
// elements of the period

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodClass {

    // Function to negate given periods
    static void toNegate(ChronoPeriod p1)
    {

        System.out.println(p1.negated());
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining period
        int year = -4;
        int months = -11;
        int days = -10;
        ChronoPeriod p1 = Period.of(year, months, days);

        toNegate(p1);
    }
}
```

**输出:**

```java
P4Y11M10D

```

**参考**:[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronoperiod . html #否定–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#negated--)