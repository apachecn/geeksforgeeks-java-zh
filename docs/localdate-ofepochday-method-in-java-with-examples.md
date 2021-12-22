# Java 中的 LocalDate ofEpochDay()方法，带示例

> 原文:[https://www . geesforgeks . org/local date-ofepochday-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-ofepochday-method-in-java-with-examples/)

Java 中 **LocalDate** 类的**of pochday(长 epochDay)** 方法用于从历元日计数中获取 **LocalDate** 的实例。纪元日是 1970 年 1 月 1 日。这被认为是新纪元的开始。该方法通过将过去的天数添加到纪元日期(即 01-01-1970)中来返回本地日期。假设将 2 作为参数传递，该方法将返回 03-01-1970(从纪元日(DD)开始，将 2 添加到“01”)。类似地，如果 365 被通过，那么整个新的一年将被添加到纪元日期。

**语法:**

```java
public static LocalDate ofEpochDay(long epochDay)

```

**参数:**该方法接受一个参数 **epochDay** 作为换算基数。

**返回值:**该方法返回转换后的**本地日期**。

**异常:**如果纪元日超出支持的日期范围，此方法将抛出**日期时间异常**。

下面的程序说明了 Java 中的长 EpochDay 方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalDate.ofEpochDay(long epochDay) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create LocalDate object
        LocalDate localdate
            = LocalDate.ofEpochDay(100);

        // Display full date
        System.out.println("Date: "
                           + localdate);
    }
}
```

**Output:**

```java
Date: 1970-04-11

```

**程序 2:**

```java
// Java program to demonstrate
// LocalDate.ofEpochDay(long epochDay) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create LocalDate object
        LocalDate localdate
            = LocalDate.ofEpochDay(365);

        // Display date
        System.out.println("Date: "
                           + localdate);
    }
}
```

**Output:**

```java
Date: 1971-01-01

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # ofEpochDay(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#ofEpochDay(long))