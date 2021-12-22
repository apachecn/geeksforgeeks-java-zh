# Java 中的 Instant with()方法，示例

> 原文:[https://www . geesforgeks . org/instant-with-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-with-method-in-java-with-examples/)

在 Instant 类中，根据传递给它的参数，有两种类型的 with()方法。

### 带(临时调节器)

**用 **Instant** 类的**方法使用临时调整器调整该瞬间，调整后返回调整瞬间的副本。使用指定的调整器策略对象进行调整。Instant 的这个实例是不可变的，不受这个方法调用的影响。

**语法:**

```java
public Instant with(TemporalAdjuster adjuster)

```

**参数:**该方法接受**调节器**作为参数，调节器使用该参数。

**返回值:**该方法根据调整后的值返回一个即时值。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了用()方法:
**程序 1:**

```java
// Java program to demonstrate
// Instant.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant local
            = Instant.parse(
                "2018-12-30T19:34:50.63Z");

        // print instance
        System.out.println("Instant before"
                           + " adjustment: "
                           + local);

        // apply with method of Instant class
        Instant updatedlocal
            = local.with(Instant.EPOCH);

        // print instance
        System.out.println("Instant after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

**Output:**

```java
Instant before adjustment: 2018-12-30T19:34:50.630Z
Instant after adjustment: 1970-01-01T00:00:00Z

```

### 带(临时字段，长新值)

**使用 **Instant** 类的(临时字段，长新值)**方法，用于将 Instant 的指定字段设置为新值，并返回新时间的副本。此方法可用于更改任何支持的字段，如年、日、月、小时、分钟或秒。如果由于字段不受支持或其他原因而无法设置新值，则会引发异常。Instant 的这个实例是不可变的，不受这个方法调用的影响。

**语法:**

```java
public Instant with(TemporalField field, long newValue)

```

**参数:**此方法接受**字段**和**新值**，前者是要在结果中设置的字段，后者是结果中字段的新值作为参数。

**返回值:**该方法返回一个带有指定字段集的即时消息。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **unsupportedtemporaltypexception**–如果不支持该字段。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了用()方法:
**程序 1:**

```java
// Java program to demonstrate
// Instant.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant local
            = Instant.parse(
                "2021-01-01T19:55:30Z");

        // print instance
        System.out.println("Instant before"
                           + " applying method: "
                           + local);

        // apply with method of Instant class
        Instant updatedlocal
            = local.with(
                ChronoField.INSTANT_SECONDS,
                45000000000);

        // print instance
        System.out.println("Instant after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**Output:**

```java
Instant before applying method: 2021-01-01T19:55:30Z
Instant after applying method: 1970-01-01T00:00:45Z

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # with(Java . time . temporaladjuster)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#with(java.time.temporal.TemporalAdjuster))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # with(Java . time . temporal field，long)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#with(java.time.temporal.TemporalField, long))