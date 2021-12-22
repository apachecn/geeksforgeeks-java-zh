# Java 中(日期、时间)方法的 LocalDateTime，示例

> 原文:[https://www . geesforgeks . org/local datetime-of date-time-in-Java-method-with-examples/](https://www.geeksforgeeks.org/localdatetime-ofdate-time-method-in-java-with-examples/)

Java 中 **LocalDateTime** 类的**(local date date，LocalTime time)** 方法使用日期和时间两个输入参数来获取 **LocalDateTime** 的一个实例。最初，会创建两个独立的实例。一个是本地日期类型，另一个是本地时间类型。然后这些被合并以创建一个本地日期时间。

**语法:**

```
public static LocalDateTime of(LocalDate date, 
                               LocalTime time)

```

**参数:**该方法接受两个参数:

*   **日期**–为本地日期类型，代表本地日期。
*   **时间**–为 LocalTime 类型，代表当地时间。

**返回值:**该方法返回**本地日期时间**。

**异常:**此方法不抛出任何异常。

下面的程序说明了在 Java 中使用(LocalDate，LocalTime)方法的过程:

**程序 1:**

```
// Java program to demonstrate
// LocalDateTime.of(LocalDate date,
// LocalTime time) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create LocalDate object
        // using LocalDate.of() method
        LocalDate date
            = LocalDate.of(2020, 5, 13);

        // Create LocalTime object
        // using LocalTime.of() method
        LocalTime time = LocalTime.of(6, 30);

        // Create LocalDateTime object
        LocalDateTime localdatetime
            = LocalDateTime.of(date, time);

        // Print full date and time
        System.out.println(
            "DateTime: " + localdatetime);
    }
}
```

**Output:**

```
DateTime: 2020-05-13T06:30

```

**程序 2:**

```
// Java program to demonstrate
// LocalDateTime.of(LocalDate date,
// LocalTime time) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create LocalDate object
        // using LocalDate.of() method
        LocalDate date
            = LocalDate.of(2019, 12, 31);

        // Create LocalTime object
        // using LocalTime.of() method
        LocalTime time = LocalTime.of(6, 30, 45);

        // Create LocalDateTime object
        LocalDateTime localdatetime
            = LocalDateTime.of(date, time);

        // Print full date and time
        System.out.println(
            "DateTime: " + localdatetime);
    }
}
```

**Output:**

```
DateTime: 2019-12-31T06:30:45

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # of(Java . time . local date，java.time.LocalTime)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#of(java.time.LocalDate, java.time.LocalTime))