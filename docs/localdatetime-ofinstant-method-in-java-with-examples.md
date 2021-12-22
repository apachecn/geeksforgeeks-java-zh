# Java 中的 LocalDateTime ofInstant()方法，示例

> 原文:[https://www . geesforgeks . org/local datetime-of instant-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-ofinstant-method-in-java-with-examples/)

Java 中 **LocalDateTime** 类的**方法用于使用一个即时和区域 Id 创建 **LocalDateTime** 的一个实例。这两个参数被传递给方法，方法根据这两个参数返回 LocalDateTime。本地日期时间的计算遵循以下步骤。**

***   The zone identification and instant are used to obtain the offset from Universal Coordinated Time/Greenwich Mean Time, because each instance can only have one valid offset.*   Finally, calculate the local date and time using the instant and the obtained offset.**

**语法:**

```java
public static LocalDateTime 
       ofInstant(Instant instant,
                 ZoneId zone)

```

**参数:**该方法接受两个参数:

*   **–It is an instant type, which indicates the moment passed by the creation of localdatetime.**
***   **Area** –It belongs to the area identification type and represents the time zone used to create the offset.**

****返回值:**该方法返回**本地日期时间**。**

****异常:**如果结果超出支持范围，该方法抛出**日期时间异常**。**

**下面的程序说明了 Java 中的即时(Instant instant，ZoneId zone)方法:**

****程序 1:****

```java
// Java program to demonstrate
// LocalDateTime.ofInstant(
// Instant instant, ZoneId zone) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create LocalDateTime object
        LocalDateTime localdatetime
            = LocalDateTime.ofInstant(
                Instant.now(),
                ZoneId.systemDefault());

        // Print full date
        System.out.println(
            "Date: " + localdatetime);
    }
}
```

****输出:**

```java
Date: 2020-05-13T12:40:38.087

```

**程序二:**

```java
// Java program to demonstrate
// LocalDateTime.ofInstant(
// Instant instant, ZoneId zone) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create LocalDateTime object
        LocalDateTime localdatetime
            = LocalDateTime.ofInstant(
                Instant.now(),
                ZoneId.systemDefault());

        // Print year only
        System.out.println(
            "Year: " + localdatetime.getYear());
    }
}
```

**输出:**

```java
Year: 2020

```

**参考:**[https://docs . Oracle . com/javae/10/docs/API/Java/time/local datetime . html # office constant(Java . time . instant，java.time.ZoneId)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#ofInstant(java.time.Instant, java.time.ZoneId))**