# Java 中的 ChronoLocalDate toEpochDay()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-toepochday-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-toepochday-method-in-java-with-examples/)

一个**时间日期**界面的 **toEpochDay()** 方法用来获取这个日期作为一个 EpochDay。EpochDay 是从 1970-01-01 (ISO)的 0 EpochDay 开始的一天的计数。输出将采用国际标准化组织 8601 格式。

**语法:**

```java
default long toEpochDay()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回**一个长值**，即该日期的 EpochDay 计数，不为空。

下面的程序说明了 toEpochDay()方法:

**程序 1:**

```java
// Java program to demonstrate
// ChronoLocalDate.toEpochDay() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDate object
        ChronoLocalDate localD
            = LocalDate.parse("2018-12-06");

        // print ChronoLocalDate
        System.out.println("ChronoLocalDate as EpochDay: "
                           + localD.toEpochDay());
    }
}
```

**输出:**

```java
ChronoLocalDate as EpochDay: 17871

```

**程序二:**

```java
// Java program to demonstrate
// ChronoLocalDate.toEpochDay() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDate object
        ChronoLocalDate localD
            = LocalDate.parse("2021-06-30");

        // print ChronoLocalDate
        System.out.println("ChronoLocalDate as EpochDay: "
                           + localD.toEpochDay());
    }
}
```

**输出:**

```java
ChronoLocalDate as EpochDay: 18808

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldata . html # toEpochDay–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#toEpochDay--)