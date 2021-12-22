# Java 中的 MonthDay getDayOfMonth()方法，带示例

> 原文:[https://www . geesforgeks . org/monthday-getdayofmonth-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-getdayofmonth-method-in-java-with-examples/)

Java 中**月日类**的 **getDayOfMonth()** 方法得到月日字段。

**语法:**

```
public int getDayOfMonth()
```

**参数:**此方法不接受参数。

**返回:**函数返回月中的某一天，从 1 到 31。

下面的程序说明了**月日. getDayOfMonth()** 方法:

**程序 1:**

```
// Program to illustrate the getDayOfMonth() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        MonthDay tm1 = MonthDay.parse("--12-06");

        // Uses the function
        LocalDate dt1 = tm1.atYear(2018);

        // Prints the day
        System.out.println(dt1.getDayOfMonth());
    }
}
```

**输出:**

```
6

```

**程序二:**

```
// Program to illustrate the getDayOfMonth() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        MonthDay tm1 = MonthDay.parse("--01-19");

        // Uses the function
        LocalDate dt1 = tm1.atYear(2018);

        // Prints the day
        System.out.println(dt1.getDayOfMonth());
    }
}
```

**输出:**

```
19

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/monthday . html # getDayOfMonth–](https://docs.oracle.com/javase/8/docs/api/java/time/MonthDay.html#getDayOfMonth--)