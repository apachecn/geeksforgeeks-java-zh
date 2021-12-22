# Java 中的 LocalDateTime getYear()方法，带示例

> 原文:[https://www . geesforgeks . org/local datetime-getyear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-getyear-method-in-java-with-examples/)

**本地日期时间类**的 **getYear()** 方法用于返回年份字段。此方法返回从最小年到最大年的原始整数值。

**语法:**

```java
public int getYear()

```

**参数:**此方法不接受任何参数。

**返回:**该方法返回一个**整数值**，它是从 MIN_YEAR 到 MAX_YEAR 的年份的原始 int 值。

下面的程序说明了 LocalDateTime.getYear()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalDateTime.getYear() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2018-12-03T12:39:10");

        // get Year
        int year = local.getYear();

        // print result
        System.out.println("Year: "
                           + year);
    }
}
```

**输出:**

```java
Year: 2018

```

**程序二:**

```java
// Java program to demonstrate
// LocalDateTime.getYear() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2019-01-28T22:29:10");

        // get Year
        int year = local.getYear();

        // print result
        System.out.println("Year: "
                           + year);
    }
}
```

**输出:**

```java
Year: 2019

```

参考:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # getYear()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#getYear())