# Java 中的计时周期减法()方法，示例

> 原文:[https://www . geesforgeks . org/chronoperiod-减法器-Java-in-method-with-examples/](https://www.geeksforgeeks.org/chronoperiod-subtractfrom-method-in-java-with-examples/)

**java.time.chrono 包**中**计时周期接口**的**减法从(时态)**方法用于将该计时周期减去指定的时态对象，作为参数传递。

**语法:**

```java
Temporal subtractFrom(Temporal temporalObject)

```

**参数:**该方法接受一个参数**时间对象**，即该时间周期内需要调整的量。它不应为空。

**返回值:**该方法返回一个相同类型的**对象**，并对其进行时间对象调整。

**异常:**此方法抛出:

*   **Abnormal date and time** : If the subtraction is not possible.
*   **Arithmetic exception** : If there is a numerical overflow.

以下示例说明了 ChronoPeriod .减法 From()方法:

**程序 1** :

```java
// Java code to show the function subtractFrom()
// to subtract the two given periods

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodDemo {

    // Driver Code
    public static void main(String[] args)
    {
        // Defining period
        int year = 4;
        int months = 11;
        int days = 10;
        ChronoPeriod p1 = Period.of(year, months, days);

        // Get the time to be adjusted
        LocalDateTime currentTime
            = LocalDateTime.now();

        // Adjust the time
        // using subtractFrom() method
        System.out.println(
            p1.subtractFrom(currentTime));
    }
}
```

**输出:**

```java
2014-07-07T14:22:21.929

```

**程序二** :

```java
// Java code to show the function subtractFrom()
// to subtract the two given periods

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodDemo {

    // Driver Code
    public static void main(String[] args)
    {
        // Defining period
        int year1 = 2;
        int months1 = 7;
        int days1 = 8;
        ChronoPeriod p1 = Period.of(year1, months1, days1);

        // Get the time to be adjusted
        LocalDateTime currentTime
            = LocalDateTime.now();

        // Adjust the time
        // using subtractFrom() method
        System.out.println(
            p1.subtractFrom(currentTime));
    }
}
```

**输出:**

```java
2016-11-09T14:22:26.600

```

**参考**:[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronoperiod . html #减法 from-Java . time . temporal-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#subtractFrom-java.time.temporal.Temporal-)