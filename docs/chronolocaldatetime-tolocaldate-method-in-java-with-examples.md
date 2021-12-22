# Java 中的 chronolocaltimetolocaldate()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldetate-tolocaldate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-tolocaldate-method-in-java-with-examples/)

**计时本地日期时间**接口的 **toLocalDate()** 方法用于将该计时本地日期时间转换为本地日期。该方法返回此 ChronoLocalDateTime 的 LocalDate 部分。

**语法:**

```java
default LocalDate toLocalDate()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回**本地日期**，即该时间本地日期时间的本地日期

下面的程序说明了 toLocalDate()方法:

**程序 1:**

```java
// Java program to demonstrate
// ChronoLocalDateTime.toLocalDate() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoLocalDateTime object
        ChronoLocalDateTime time
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        // print ChronoLocalDateTime
        System.out.println("ChronoLocalDateTime: "
                           + time);

        // print result
        System.out.println("LocalDate: "
                           + time.toLocalDate());
    }
}
```

**输出:**

```java
ChronoLocalDateTime: 2019-12-31T19:15:30
LocalDate: 2019-12-31

```

**程序二:**

```java
// Java program to demonstrate
// ChronoLocalDateTime.toLocalDate() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoLocalDateTime object
        ChronoLocalDateTime time
            = LocalDateTime.parse(
                "2018-10-25T23:12:31.123");

        // print ChronoLocalDateTime
        System.out.println("ChronoLocalDateTime: "
                           + time);

        // print result
        System.out.println("LocalDate: "
                           + time.toLocalDate());
    }
}
```

**输出:**

```java
ChronoLocalDateTime: 2018-10-25T23:12:31.123
LocalDate: 2018-10-25

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/chrono/chronical datetime . html # tolocaldate--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#toLocalDate--)