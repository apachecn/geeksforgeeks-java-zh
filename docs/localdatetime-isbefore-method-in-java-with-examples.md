# Java 中的 LocalDateTime isBefore()方法，示例

> 原文:[https://www . geesforgeks . org/local datetime-is before-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-isbefore-method-in-java-with-examples/)

Java 中 **LocalDateTime 类**的 **isBefore()** 方法检查该日期是否在指定的日期时间之前。

**语法:**

```java
public boolean isBefore(ChronoLocalDateTime other)
```

**参数:**此方法接受一个参数**其他**，它是要比较的另一个日期时间。它不应为空。

**返回:**如果该日期时间在指定日期时间之前，该函数返回**布尔值:**。

下面的程序说明了 LocalDateTime.isBefore()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program to illustrate the isBefore() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-11-03T12:45:30");

        // Prints the date
        System.out.println("Date 1: " + dt1);

        // Parses the date
        LocalDateTime dt2
            = LocalDateTime
                  .parse("2016-12-04T12:45:30");

        // Prints the date
        System.out.println("Date 2: " + dt2);

        // Compares both dates
        System.out.println("Is Date 1 before Date 2: "
                           + dt1.isBefore(dt2));
    }
}
```

**Output:** 

```java
Date 1: 2018-11-03T12:45:30
Date 2: 2016-12-04T12:45:30
Is Date 1 before Date 2: false
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program to illustrate the isBefore() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-11-03T12:45:30");

        // Prints the date
        System.out.println("Date 1: " + dt1);

        // Parses the date
        LocalDateTime dt2
            = LocalDateTime
                  .parse("2019-12-04T12:45:30");

        // Prints the date
        System.out.println("Date 2: " + dt2);

        // Compares both dates
        System.out.println("Is Date 1 before Date 2: "
                           + dt1.isBefore(dt2));
    }
}
```

**Output:** 

```java
Date 1: 2018-11-03T12:45:30
Date 2: 2019-12-04T12:45:30
Is Date 1 before Date 2: true
```

**参考:**[https://docs . Oracle . com/javae/10/docs/API/Java/time/local datetime . html # isefore(Java . time . chrono . chrolcaldatetime)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#isBefore(java.time.chrono.ChronoLocalDateTime))