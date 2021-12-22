# Java 中的 LocalDate withYear()方法，示例

> 原文:[https://www . geesforgeks . org/local date-with year-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-withyear-method-in-java-with-examples/)

Java 中 **LocalDate 类**的 **withYear()** 方法返回一个更改了年份的 LocalDate 的副本。

**语法:**

```java
public LocalDate withYear(int year)
```

**参数:**该方法接受一个强制参数**年份**，指定要在结果中设置的年份，该年份可以在 MIN_YEAR 到 MAX_YEAR 的范围内。

**返回:**该函数根据请求年份的日期返回一个 LocalDate，而不是 null。

**异常**:当年份值无效时，函数抛出**日期时间异常**。

下面的程序说明了 **LocalDate.withYear()** 方法:

**程序 1:**

```java
// Program to illustrate the withYear() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Parses the date
        LocalDate dt1 = LocalDate.parse("2018-12-07");
        LocalDate result = dt1.withYear(2018);

        // Prints the date with year
        System.out.println("The date with year is: " + result);
    }
}
```

**输出:**

```java
The date with year is: 2018-12-07

```

**程序二:**

```java
// Program to illustrate the withYear() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Parses the date
        LocalDate dt1 = LocalDate.parse("2018-01-07");
        LocalDate result = dt1.withYear(2014);

        // Prints the date with year
        System.out.println("The date with year is: " + result);
    }
}
```

**输出:**

```java
The date with year is: 2014-01-07

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # with year(int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#withYear(int))