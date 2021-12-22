# Java 中的 Instant from()方法，示例

> 原文:[https://www . geesforgeks . org/instant-from-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-from-method-in-java-with-examples/)

**Instant 类**的 **from()** 方法有助于从作为参数传递的临时进程对象获取 Instant 的实例。临时处理器代表一组任意的日期和时间信息，这种方法有助于根据指定的临时处理器对象获得即时消息。TempralAccessor 对象到 instant 的转换提取 INSTANT_SECONDS 和 NANO_OF_SECOND 字段。

**语法:**

```
public static Instant
    from(TemporalAccessor temporal)

```

**参数:**该方法只接受一个代表时态对象的参数**时态**。它不应为空。

**返回:**该方法从临时处理器对象返回**即时**对象。它不应为空。

**异常:**如果方法无法将时态对象转换为即时，此方法将抛出**日期时间异常**。

下面的程序说明了 from()方法:

**程序 1:**

```
// Java program to demonstrate
// Instant.from() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zonedDateTime
            = ZonedDateTime.now();

        // print Value
        System.out.println("ZonedDateTime: "
                           + zonedDateTime);

        // create a Instant object using
        // from() method
        Instant result = Instant.from(zonedDateTime);

        // print result
        System.out.println("Instant: "
                           + result);
    }
}
```

**输出:**

```
ZonedDateTime: 2018-11-27T04:58:47.691Z[Etc/UTC]
Instant: 2018-11-27T04:58:47.691Z

```

**程序二:**

```
// Java program to demonstrate
// Instant.from() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a OffsetDateTime object
        OffsetDateTime offset
            = OffsetDateTime.now();

        // print Value
        System.out.println("OffsetDateTime: "
                           + offset);

        // apply from() method
        Instant result = Instant.from(offset);

        // print result
        System.out.println("Instant: "
                           + result);
    }
}
```

**输出:**

```
OffsetDateTime: 2018-11-27T04:58:50.588Z
Instant: 2018-11-27T04:58:50.588Z

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html #来自(Java . time . temporal . temporalacessor)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#from(java.time.temporal.TemporalAccessor))