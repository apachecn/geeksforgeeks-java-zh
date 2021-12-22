# Java 中带有 DayOfYear()方法的 LocalDateTime，示例

> 原文:[https://www . geesforgeks . org/local datetime-with dayof year-in-Java-method-with-examples/](https://www.geeksforgeeks.org/localdatetime-withdayofyear-method-in-java-with-examples/)

Java 中 **LocalDateTime 类**的 **withDayOfYear()** 方法用于获取该 LocalDateTime 的副本，DayOfYear 被更改为 dayOfYear，并作为参数传递给该方法。该本地日期时间的其余值保持不变。

**语法:**

```
public LocalDateTime withDayOfYear(int dayOfYear)
```

**参数:**该方法接受一个强制参数**day fyear**，该参数指定要在结果本地日期时间实例中设置的 day fyear。该日期的值可以从 1 到 366。

**返回:**该函数返回一个**本地日期时间实例**，其中 dayOfYear 被更改为 dayOfYear，并作为参数传递给该方法。该本地日期时间的其余值保持不变。

**异常**:如果 dayOfYear 值无效，函数抛出**日期时间异常**。

下面的程序说明了 LocalDateTime.withDayOfYear()方法:

**程序 1:**

```
// Program to illustrate the withDayOfYear() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Get the LocalDateTime instance
        LocalDateTime dt = LocalDateTime.now();

        // Get the String representation of this LocalDateTime
        System.out.println("Original LocalDateTime: "
                           + dt.toString());

        // Get a new LocalDateTime with dayOfYear 1
        System.out.println("New LocalDateTime: "
                           + dt.withDayOfYear(1));
    }
}
```

**输出:**

```
Original LocalDateTime: 2018-11-30T12:54:35.320
New LocalDateTime: 2018-01-01T12:54:35.320

```

**程序二:**

```
// Program to illustrate the withDayOfYear() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Get the LocalDateTime instance
        LocalDateTime dt
            = LocalDateTime
                  .parse("2015-04-06T10:15:30");

        // Get the String representation of this LocalDateTime
        System.out.println("Original LocalDateTime: "
                           + dt.toString());

        // Get a new LocalDateTime with dayOfYear 365
        System.out.println("New LocalDateTime: "
                           + dt.withDayOfYear(365));
    }
}
```

**输出:**

```
Original LocalDateTime: 2015-04-06T10:15:30
New LocalDateTime: 2015-12-31T10:15:30

```

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # withDayOfYear(int)