# Java 中 LocalTime from()方法，示例

> 原文:[https://www . geesforgeks . org/local time-from-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-from-method-in-java-with-examples/)

**本地时间类**的 **from()** 方法有助于从作为参数传递给方法的临时进程对象中获取本地时间的实例。临时进程代表一组任意的日期和时间信息，该方法有助于根据指定的临时进程对象获取本地时间。

**语法:**

```
public static LocalTime from(TemporalAccessor temporal)

```

**参数:**该方法接受单个参数**时态**，即时态对象。它不应为空。

**返回值:**该方法从时态对象返回**当地时间**，不为空

**异常:**如果无法转换为本地时间，该方法抛出**日期时间异常**。

下面的程序说明了 from()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalTime.from() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a ZonedDateTime object
        ZonedDateTime zonedDateTime
            = ZonedDateTime.now();

        // apply form()
        LocalTime value
            = LocalTime.from(zonedDateTime);

        // print result
        System.out.println("LocalTime value : "
                           + value);
    }
}
```

**输出:**

```
LocalTime value : 06:17:32.760

```

**程序二:**

```
// Java program to demonstrate
// LocalTime.from() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a OffsetDateTime object
        OffsetDateTime offset
            = OffsetDateTime.now();

        // apply form()
        LocalTime value = LocalTime.from(offset);

        // print result
        System.out.println("LocalTime value : "
                           + value);
    }
}
```

**输出:**

```
LocalTime value : 06:17:35.131

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/localtime . html # from(Java . time . temporalacessor)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#from(java.time.temporal.TemporalAccessor))