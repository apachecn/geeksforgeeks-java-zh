# Java 中的 LocalTime atDate()方法，示例

> 原文:[https://www . geesforgeks . org/local time-at date-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-atdate-method-in-java-with-examples/)

**LocalTime 类**的 **atDate()** 方法用于将这个 LocalTime 对象与 LocalDate 对象组合起来，创建一个 LocalDateTime。日期和时间的所有可能组合都有效。

**语法:**

```java
public LocalDateTime atDate(LocalDate date)

```

**参数:**该方法接受单个参数**日期**，即与 LocalTime 对象组合的日期，不为空。

**返回值:**该方法将 LocalTime 和 LocalDate 合并后返回 LocalDateTime 对象，不为空。

以下程序说明了 atDate()方法:
**程序 1:**

```java
// Java program to demonstrate
// LocalTime.atDate() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime Object
        LocalTime time
            = LocalTime.parse("09:32:42");

        // create LocalDate Object
        LocalDate date
            = LocalDate.parse("2018-12-05");

        // apply atDate()
        LocalDateTime local
            = time.atDate(date);

        // print LocalDateTime
        System.out.println("Date and Time:"
                           + local.toString());
    }
}
```

**Output:**

```java
Date and Time:2018-12-05T09:32:42

```

**程序 2:**

```java
// Java program to demonstrate
// LocalTime.atDate() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime Object
        LocalTime time = LocalTime.parse("18:12:49");

        // create LocalDate Object
        LocalDate date = LocalDate.parse("2017-12-05");

        // apply atDate()
        LocalDateTime local = time.atDate(date);

        // print LocalDateTime
        System.out.println("Date and Time:"
                           + local.toString());
    }
}
```

**Output:**

```java
Date and Time:2017-12-05T18:12:49

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # atDate(Java . time . local date)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#atDate(java.time.LocalDate))