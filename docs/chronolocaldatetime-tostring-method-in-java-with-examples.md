# Java 中的 ChronoLocalDateTime toString()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-tostring-method-in-java-with-examples/)

**计时本地日期时间**类的 **toString()** 方法用于将该计时本地日期时间转换为字符串。

**语法:**

```java
String toString()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个**字符串**，它是这个时间位置日期时间的字符串表示

下面的程序说明了 toString()方法:

**程序 1:**

```java
// Java program to demonstrate
// ChronoLocalDateTime.toString() method

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
        System.out.println("String: "
                           + time.toString());
    }
}
```

**输出:**

```java
ChronoLocalDateTime: 2019-12-31T19:15:30
String: 2019-12-31T19:15:30

```

**程序二:**

```java
// Java program to demonstrate
// ChronoLocalDateTime.toString() method

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
        System.out.println("String: "
                           + time.toString());
    }
}
```

**输出:**

```java
ChronoLocalDateTime: 2018-10-25T23:12:31.123
String: 2018-10-25T23:12:31.123

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/cron/chronical datetime . html # tostring】](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#toString--)