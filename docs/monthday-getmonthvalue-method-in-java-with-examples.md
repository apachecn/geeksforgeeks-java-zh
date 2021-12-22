# Java 中的 MonthDay getMonthValue()方法，带示例

> 原文:[https://www . geesforgeks . org/month day-getmonth value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-getmonthvalue-method-in-java-with-examples/)

Java 中 **MonthDay 类**的**getmonthvvalue()**方法获取 1 到 12 的年月字段。

**语法:**

```java
public int getMonthValue()
```

**参数:**此方法不接受参数。

**返回:**函数返回一年中的月份，从 1 到 12。

下面的程序说明了**monthday . getmonthvvalue()**方法:

**程序 1:**

```java
// Program to illustrate the getMonthValue() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        MonthDay tm1 = MonthDay.parse("--12-06");

        // Uses the function
        LocalDate dt1 = tm1.atYear(2018);

        // Prints the date
        System.out.println(dt1.getMonthValue());
    }
}
```

**输出:**

```java
12

```

**程序二:**

```java
// Program to illustrate the getMonthValue() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        MonthDay tm1 = MonthDay.parse("--01-09");

        // Uses the function
        LocalDate dt1 = tm1.atYear(2016);

        // Prints the date
        System.out.println(dt1.getMonthValue());
    }
}
```

**输出:**

```java
1

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/monthday . html # getmonthvvalue–](https://docs.oracle.com/javase/8/docs/api/java/time/MonthDay.html#getMonthValue--)