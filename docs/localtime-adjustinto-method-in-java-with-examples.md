# Java 中的 LocalTime adjustInto()方法，示例

> 原文:[https://www . geesforgeks . org/local time-adjustin to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-adjustinto-method-in-java-with-examples/)

**LocalTime 类**的 **adjustInto()** 方法用于调整指定的时间对象，使其与该 LocalTime 对象具有相同的时间。

**语法:**

```java
public Temporal adjustInto(Temporal temporal)

```

**参数:**该方法接受单个参数**时间**，该参数是需要调整的目标对象，不具体为空。

**返回值:**该方法返回**调整后的时态对象**。

**异常:**该函数抛出如下所述的两个异常:

*   **Abnormal date and time** –If adjustment is not possible
*   **Algorithm exception** -If there is a numerical overflow

以下程序说明了 adjustInto()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalTime.adjustInto() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime Object
        LocalTime local
            = LocalTime.parse("09:32:42");

        // create Zone Time
        ZonedDateTime zonetime = ZonedDateTime.now();

        // print Zone Time
        System.out.println("ZonedDateTime"
                           + " before adjustInto():"
                           + zonetime.toString());

        // apply adjustInto()
        zonetime = (ZonedDateTime)local
                       .adjustInto(zonetime);

        // print Zone Time
        System.out.println("ZonedDateTime"
                           + " after adjustInto():"
                           + zonetime.toString());
    }
}
```

**输出:**

```java
ZonedDateTime before adjustInto():2018-12-03T06:30:31.142Z[Etc/UTC]
ZonedDateTime after adjustInto():2018-12-03T09:32:42Z[Etc/UTC]

```

**程序二:**

```java
// Java program to demonstrate
// LocalTime.adjustInto() method

import java.time.*;
import java.time.temporal.Temporal;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime Object
        LocalTime local = LocalTime.parse("19:52:43");

        // create a Temporal object
        // which is equal to OffsetDateTime object
        OffsetDateTime passTemporal
            = OffsetDateTime.now();

        // print passed Value
        System.out.println("Before adjustInto() OffsetDateTime: "
                           + passTemporal);

        // apply adjustInto method
        // to adjust OffsetDateTime Temporal
        Temporal returnTemporal
            = local.adjustInto(passTemporal);

        // print results
        System.out.println("After adjustInto() OffsetDateTime: "
                           + (OffsetDateTime)returnTemporal);
    }
}
```

**输出:**

```java
Before adjustInto() OffsetDateTime: 2018-12-03T06:30:33.927Z
After adjustInto() OffsetDateTime: 2018-12-03T19:52:43Z

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # adjustInto(Java . time . temporal . temporal)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#adjustInto(java.time.temporal.Temporal))