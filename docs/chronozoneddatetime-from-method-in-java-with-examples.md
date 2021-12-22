# Java 中的 ChronoZonedDateTime from()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-from-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-from-method-in-java-with-examples/)

Java 方法中**时空数据时间**接口的 **from()** 方法从时态对象中获取一个时空数据时间的实例。

**语法** :

```
static ChronoZonedDateTime 
    from(TemporalAccessor temporal)

```

**参数**:该方法接受一个参数*时态*，指定要转换的时态对象，不为空。

**返回值**:返回时区数据时间，不为空。

**异常**:该函数只抛出*日期时间异常*，如果无法将其转换为时区数据时间，则会出现该异常。

下面的程序说明了 Java 中的 ChronoZonedDateTime 的 from()方法:

**注意**:每次运行输出都会改变。

```
// Program to illustrate the from() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {

        ChronoZonedDateTime dt
            = ZonedDateTime.from(ZonedDateTime.now());

        System.out.println(dt);
    }
}
```

**输出:**

```
2019-05-26T12:36:04.419Z[Etc/UTC]

```

**参考**:[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronozoneddatetime . html # from-Java . time .时态. temporalacessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#from-java.time.temporal.TemporalAccessor-)