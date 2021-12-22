# Java 中的 MonthDay atYear()方法，带示例

> 原文:[https://www . geesforgeks . org/month day-at year-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-atyear-method-in-java-with-examples/)

Java 中 **MonthDay 类**的 **atYear()** 方法将这个月日和一年结合起来创建一个 LocalDate。

**语法:**

```
public LocalDate atYear(int year)
```

**参数:**该方法接受一个参数**年份**，指定使用的年份，该年份在[MIN_YEAR，MAX_YEAR]范围内

**返回:**函数返回本月日和指定年份组成的本地日期，不为空。

下面的程序说明了 **MonthDay.atYear()** 方法:

**程序 1:**

```
// Program to illustrate the atYear() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        MonthDay tm = MonthDay.parse("--12-06");

        // Uses the function
        LocalDate dt = tm.atYear(2018);

        // Prints the date
        System.out.println(dt);
    }
}
```

**输出:**

```
2018-12-06

```

**程序二:**

```
// Program to illustrate the atYear() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        MonthDay tm = MonthDay.parse("--01-01");

        // Uses the function
        LocalDate dt = tm.atYear(2010);

        // Prints the date
        System.out.println(dt);
    }
}
```

**输出:**

```
2010-01-01

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/monthday . html # at year-int-](https://docs.oracle.com/javase/8/docs/api/java/time/MonthDay.html#atYear-int-)