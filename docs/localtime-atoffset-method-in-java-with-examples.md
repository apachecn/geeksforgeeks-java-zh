# Java 中的 LocalTime atOffset()方法，带示例

> 原文:[https://www . geesforgeks . org/local time-atoffset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-atoffset-method-in-java-with-examples/)

**本地时间类**的 **atOffset()** 方法用于将该时间与偏移对象组合以创建偏移时间对象。时间和偏移量的所有可能组合都有效。

**语法:**

```
public OffsetTime atOffset(ZoneOffset offset)

```

**参数:**该方法接受单个参数**偏移量**，该偏移量是要与本地时间对象组合的偏移量，不为空。

**返回值:**该方法返回由该时间和指定偏移量形成的**偏移时间**，不为空。

下面的程序说明了 atOffset()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalTime.atOffset() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime Object
        LocalTime time
            = LocalTime.parse("16:12:49");

        // create a ZoneOffset object
        // with 7200 sec means 2 hours
        ZoneOffset offset
            = ZoneOffset.ofTotalSeconds(7200);

        // apply atOffset()
        OffsetTime offsettime
            = time.atOffset(offset);

        // print LocalDateTime
        System.out.println("Offset Time:"
                           + offsettime.toString());
    }
}
```

**输出:**

```
Offset Time:16:12:49+02:00

```

**程序二:**

```
// Java program to demonstrate
// LocalTime.atOffset() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime Object
        LocalTime time
            = LocalTime.parse("17:52:49");

        // create a ZoneOffset object
        // with 3 hours 45 minutes
        ZoneOffset offset
            = ZoneOffset.ofHoursMinutes(3, 45);

        // apply atOffset()
        OffsetTime offsettime
            = time.atOffset(offset);

        // print LocalDateTime
        System.out.println("Offset Time:"
                           + offsettime.toString());
    }
}
```

**输出:**

```
Offset Time:17:52:49+03:45

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # atOffset(Java . time . zoneoffset)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#atOffset(java.time.ZoneOffset))