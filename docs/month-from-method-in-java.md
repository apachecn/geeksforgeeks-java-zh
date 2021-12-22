# Java 中的月从()方法

> 原文:[https://www.geeksforgeeks.org/month-from-method-in-java/](https://www.geeksforgeeks.org/month-from-method-in-java/)

**from()** 是 Month ENUM 的内置方法，用于从作为参数传递给它的时态对象创建 Month 实例。

**语法** :

```
static Month from( TemporalAccessor temporal )

```

**参数**:该方法接受单个参数，该参数为时态对象，不能为空。

**返回值**:这个方法返回一个从作为参数传递给它的时态对象中获得的 Month 实例。

**异常**:如果无法将时态对象转换为有效的月份实例，则抛出*日期时间异常*。

下面的程序说明了上述方法:

**程序 1** :

```
import java.time.*;
import java.time.Month;
import java.time.temporal.Temporal;

class monthEnum {
    public static void main(String[] args)
    {
        // Convert this Temporal object to month
        Month month = Month.from(ZonedDateTime.now());

        System.out.println(month);
    }
}
```

**输出:**

```
MARCH

```

**程序二** :

```
import java.time.*;
import java.time.Month;
import java.time.temporal.Temporal;

class monthEnum {
    public static void main(String[] args)
    {
        ZoneId zoneId = ZoneId.of("UTC+1");

        ZonedDateTime zonedDateTime = ZonedDateTime.of(2015, 11, 30, 23, 45, 59, 1234, zoneId);

        // Convert this Temporal object to month
        Month month = Month.from(zonedDateTime);

        System.out.println(month);
    }
}
```

**输出:**

```
NOVEMBER

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/month . html # from-Java . time . temporal accessor-](https://docs.oracle.com/javase/8/docs/api/java/time/Month.html#from-java.time.temporal.TemporalAccessor-)