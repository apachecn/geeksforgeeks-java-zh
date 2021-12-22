# Java 中的 ChronoLocalDateTime from()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-from-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-from-method-in-java-with-examples/)

**计时本地日期时间接口**的 **from()** 方法用于从作为参数传递的时态对象中获取计时本地日期时间的实例。

**语法:**

```
static ChronoLocalDateTime<T> 
        from(TemporalAccessor temporal)

```

**参数:**该方法接受一个参数**时态**，该参数指定要转换为计时本地日期时间实例的临时进程对象。它不应为空。

**返回:**函数返回**时间位置日期时间**，这是从时间对象转换而来的时间位置日期时间。

**异常**:程序抛出**日期时间异常**，如果无法将给定的日期转换为时间位置日期时间，则会抛出该异常。

下面的程序说明了 ChronoLocalDateTime.from()方法:

**程序 1:**

```
// Program to illustrate the from() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {
        ChronoLocalDateTime date
            = LocalDateTime
                  .from(ZonedDateTime.now());

        System.out.println(date);
    }
}
```

**输出:**

```
2019-05-29T11:53:52.135

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldatetime . html # from-Java . time .时态. temporalacessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#from-java.time.temporal.TemporalAccessor-)