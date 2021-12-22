# Java 中的 LocalDateTime getDayOfYear()方法，带示例

> 原文:[https://www . geesforgeks . org/local datetime-getdayofyear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-getdayofyear-method-in-java-with-examples/)

**本地日期时间类**的**getdayofyeear()**方法用于返回年中的日期字段。此方法返回一个介于 1 到 365 之间的整数值(闰年为 366)，即一年中的天数。

**语法:**

```
public int getDayOfYear()

```

**参数:**此方法不接受任何参数。

**返回:**该方法返回一个**整数值**，代表一年中的某一天，范围从 1 到 365(闰年为 366)。

下面的程序说明了 LocalDateTime.getDayOfYear()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalDateTime.getDayOfYear() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2018-12-03T12:39:10");

        // get DayOfYear
        int dayOfYear = local.getDayOfYear();

        // print result
        System.out.println("DayOfYear: "
                           + dayOfYear);
    }
}
```

**输出:**

```
DayOfYear: 337

```

**程序二:**

```
// Java program to demonstrate
// LocalDateTime.getDayOfYear() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2019-01-28T22:29:10");

        // get DayOfYear
        int dayOfYear = local.getDayOfYear();

        // print result
        System.out.println("DayOfYear: "
                           + dayOfYear);
    }
}
```

**输出:**

```
DayOfYear: 28

```

参考:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # getDayOfYear()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#getDayOfYear())