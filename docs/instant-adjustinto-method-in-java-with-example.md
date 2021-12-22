# Java 中的即时调整()方法，示例

> 原文:[https://www . geesforgeks . org/instant-adjustin to-method-in-Java-with-example/](https://www.geeksforgeeks.org/instant-adjustinto-method-in-java-with-example/)

**即时类**的**调整(时态时态)**方法调整传递的时态对象，使其具有应用该方法的瞬间。

**语法:**

```java
public Temporal adjustInto(Temporal temporal)
```

**参数:**该方法接受一个参数**时间**，该参数是要调整的目标时间对象。它不应为空。

**返回值:**该方法返回调整后的时态对象。

**异常:**此方法抛出以下异常:

*   **datetimeexception** If this method cannot be adjusted.
*   **Arithmetic exception** If there is a numerical overflow during adjustment.

下面的程序说明了 Instant.adjustInto()方法:

**程序 1:**

```java
// Java program to demonstrate
// Instant.adjustInto() method

import java.time.*;
import java.time.temporal.Temporal;

public class GFG {

    public static void main(String[] args)
    {

        // create an instance object
        Instant instant
            = Instant.parse("2018-11-20T16:55:30.00Z");

        // create a Temporal object
        // which is equal to OffsetDateTime object
        OffsetDateTime passTemporal
            = OffsetDateTime.now();

        // print passed Value
        System.out.println("Passed Value: "
                           + passTemporal);

        // apply adjustInto method
        // to adjust OffsetDateTime Temporal
        // to instant object
        Temporal returnTemporal
            = instant.adjustInto(passTemporal);

        // print results
        System.out.println("Returned Value: "
                           + (OffsetDateTime)returnTemporal);
    }
}
```

**输出:**

```java
Passed Value: 2018-11-22T09:22:17.297Z
Returned Value: 2018-11-20T16:55:30Z

```

**程序二:**

```java
// Java program to demonstrate
// Instant.adjustInto() method

import java.time.*;
import java.time.temporal.Temporal;

public class GFG {
    public static void main(String[] args)
    {

        // create an instance object
        Instant instant
            = Instant.parse("2018-11-17T06:50:39.00Z");

        // create a Temporal object
        // which is equal to ZonedDateTime object
        ZonedDateTime passTemporal
            = ZonedDateTime.now();

        // print passed Value
        System.out.println("Passed Value: "
                           + passTemporal);

        // apply adjustInto method
        // to adjust ZonedDateTime Temporal
        // to instant object
        Temporal returnTemporal
            = instant.adjustInto(passTemporal);

        // print results
        System.out.println("Returned Value: "
                           + (ZonedDateTime)returnTemporal);
    }
}
```

**输出:**

```java
Passed Value: 2018-11-22T09:22:20.995Z[Etc/UTC]
Returned Value: 2018-11-17T06:50:39Z[Etc/UTC]

```

**程序 3:**

```java
// Java program to demonstrate
// Instant.adjustInto() method

import java.time.*;
import java.time.temporal.Temporal;

public class GFG {
    public static void main(String[] args)
    {

        // create an instance object
        Instant instant
            = Instant.parse("2017-11-01T16:25:00.00Z");

        // create a Temporal object
        // which is equal to Instant object
        // with current Instant
        Temporal passTemporal
            = Instant.now();

        // print passed Value
        System.out.println("Passed Value: "
                           + passTemporal);

        // apply adjustInto method to adjust Temporal
        // to this instant object
        Temporal returnTemporal
            = instant.adjustInto(passTemporal);

        // print results
        System.out.println("Returned Value: "
                           + returnTemporal);
    }
}
```

**输出:**

```java
Passed Value: 2018-11-22T09:22:23.298Z
Returned Value: 2017-11-01T16:25:00Z

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # adjustInto(Java . time . temporal . temporal)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#adjustInto(java.time.temporal.Temporal))