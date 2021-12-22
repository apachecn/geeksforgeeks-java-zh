# Java 中的 LocalDateTime 等于()方法，示例

> 原文:[https://www . geesforgeks . org/local datetime-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-equals-method-in-java-with-examples/)

Java 中 **LocalDateTime 类**的 **equals()** 方法检查这个日期时间是否等于另一个日期时间。另一个日期时间作为参数传递。此方法返回一个显示相同内容的布尔值。

**语法:**

```java
public boolean equals(Object date2)

```

**参数:**该方法接受参数**日期 2** ，该参数检查该日期时间是否等于另一个日期时间。

**返回:**如果该值等于另一个日期时间，则该函数返回一个**布尔值**。

下面的程序说明了 LocalDateTime.equals()方法:

**程序 1:**

```java
// Java program to illustrate the equals() method

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
                  .parse("2018-11-03T12:45:30");

        // Prints the date
        System.out.println("Date 2: " + dt2);

        // Compares the date
        System.out.println("Is Date 1 "
                           + "equal to Date 2: "
                           + dt2.equals(dt1));
    }
}
```

**输出:**

```java
Date 1: 2018-11-03T12:45:30
Date 2: 2018-11-03T12:45:30
Is Date 1 equal to Date 2: true

```

**程序二:**

```java
// Program to illustrate the equals() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Parses the date
        LocalDateTime dt1
            = LocalDateTime
                  .parse("1998-01-05T06:20:10");

        // Prints the date
        System.out.println("Date 1: " + dt1);

        // Parses the date
        LocalDateTime dt2
            = LocalDateTime
                  .parse("2018-11-03T12:45:30");

        // Prints the date
        System.out.println("Date 2: " + dt2);

        // Compares the date
        System.out.println("Is Date 1 "
                           + "equal to Date 2: "
                           + dt2.equals(dt1));
    }
}
```

**输出:**

```java
Date 1: 1998-01-05T06:20:10
Date 2: 2018-11-03T12:45:30
Is Date 1 equal to Date 2: false

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # equals(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#equals(java.lang.Object))