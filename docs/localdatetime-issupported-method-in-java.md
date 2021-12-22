# Java 中的 LocalDateTime isSupported()方法

> 原文:[https://www . geesforgeks . org/local datetime-issupported-method-in-Java/](https://www.geeksforgeeks.org/localdatetime-issupported-method-in-java/)

Java 中 **LocalDateTime 类**的 **isSupported()** 方法检查是否支持指定的单位或字段。

**语法:**

```
public boolean isSupported(TemporalUnit unit)
           or
public boolean isSupported(TemporalField field)

```

**参数:**这个方法接受一个参数*字段*指定要检查的字段，null 返回 false 或者它接受一个参数*单位*指定要检查的单位，null 返回 false。

**返回:**如果在该日期支持*字段*的*单元*，则该函数返回真，否则返回假。

下面的程序说明了 LocalDateTime.isSupported()方法:

**程序 1:**

```
// Program to illustrate the isSupported(TemporalUnit) method

import java.util.*;
import java.time.*;
import java.time.temporal.ChronoUnit;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDateTime dt1
            = LocalDateTime.parse("2018-11-03T12:45:30");

        // Prints the date
        System.out.println(dt1);

        System.out.println(dt1.isSupported(ChronoUnit.DAYS));
    }
}
```

**输出:**

```
2018-11-03T12:45:30
true

```

**程序二:**

```
// Program to illustrate the isSupported(TemporalField) method

import java.util.*;
import java.time.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDateTime dt1
            = LocalDateTime.parse("2018-11-03T12:45:30");

        // Prints the date
        System.out.println(dt1);

        System.out.println(
            dt1
                .isSupported(ChronoField.DAY_OF_WEEK));
    }
}
```

**输出:**

```
2018-11-03T12:45:30
true

```

参考:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # isSupported(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#isSupported(java.time.temporal.TemporalField))