# Java 中的 MonthDay getMonth()方法，带示例

> 原文:[https://www . geesforgeks . org/month day-get month-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-getmonth-method-in-java-with-examples/)

Java 中 **MonthDay 类**的 **getMonth()** 方法从时态对象中获取 MonthDay 的一个实例。

**语法:**

```
public Month getMonth()
```

**参数:**此方法不接受参数。

**返回:**函数返回一年中的月份，不为空。

下面的程序说明了 **MonthDay.getMonth()** 方法:

**程序 1:**

```
// Program to illustrate the getMonth() method

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
        System.out.println(dt1.getMonth());
    }
}
```

**输出:**

```
DECEMBER

```

**程序二:**

```
// Program to illustrate the getMonth() method

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
        System.out.println(dt1.getMonth());
    }
}
```

**输出:**

```
JANUARY

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/monthday . html # getMonth–](https://docs.oracle.com/javase/8/docs/api/java/time/MonthDay.html#getMonth--)