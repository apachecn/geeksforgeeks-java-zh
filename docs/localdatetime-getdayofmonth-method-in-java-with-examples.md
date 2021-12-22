# Java 中的 LocalDateTime getDayOfMonth()方法，带示例

> 原文:[https://www . geesforgeks . org/local datetime-getdayofmonth-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-getdayofmonth-method-in-java-with-examples/)

**本地日期时间类**的 **getDayOfMonth()** 方法用于返回月日字段。此方法返回一个范围从 1 到 31 的整数值，即一个月的日期。

**语法:**

```
public int getDayOfMonth()

```

**参数:**此方法不接受任何参数。

**返回:**该方法返回一个**整数值**，代表一个月中的某一天，范围从 1 到 31。

下面的程序说明了 LocalDateTime.getDayOfMonth()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalDateTime.getDayOfMonth() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2018-12-03T12:39:10");

        // get DayOfMonth
        int dayOfMonth = local.getDayOfMonth();

        // print result
        System.out.println("DayOfMonth: "
                           + dayOfMonth);
    }
}
```

**输出:**

```
DayOfMonth: 3

```

**程序二:**

```
// Java program to demonstrate
// LocalDateTime.getDayOfMonth() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2019-01-28T22:29:10");

        // get DayOfMonth
        int dayOfMonth = local.getDayOfMonth();

        // print result
        System.out.println("DayOfMonth: "
                           + dayOfMonth);
    }
}
```

**输出:**

```
DayOfMonth: 28

```

参考:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # getDayOfMonth()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#getDayOfMonth())