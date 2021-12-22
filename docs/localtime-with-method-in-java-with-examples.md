# Java 中带()方法的 LocalTime，示例

> 原文:[https://www . geesforgeks . org/local time-with-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-with-method-in-java-with-examples/)

在 LocalTime 类中，根据传递给它的参数，有两种类型的 with()方法。

### 带(临时调节器)

**用**【本地时间】**类的**方法，用临时调整器调整这个时间，调整后返回调整时间的副本。使用指定的调整器策略对象进行调整。LocalTime 的这个实例是不可变的，不受这个方法调用的影响。简单的调整器用于设置其中一个字段，例如小时字段，在该字段中，更复杂的调整器可能会将时间设置为一天中的最后一个小时。

**语法:**

```
public LocalTime with(TemporalAdjuster adjuster)

```

**参数:**该方法接受**调节器**作为参数，调节器使用该参数。

**返回值:**该方法根据调整后的值返回一个本地时间。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了用()方法:
**程序 1:**

```
// Java program to demonstrate
// LocalTime.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime local
            = LocalTime.parse(
                "13:08:56");

        // print instance
        System.out.println("LocalTime before"
                           + " adjustment: "
                           + local);

        // apply with method of LocalTime class
        LocalTime updatedlocal
            = local.with(LocalTime.MIDNIGHT);

        // print instance
        System.out.println("LocalTime after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

**Output:**

```
LocalTime before adjustment: 13:08:56
LocalTime after adjustment: 00:00

```

### 带(临时字段，长新值)

**使用 **LocalTime** 类的(临时字段，长 newValue)** 方法，用于将 LocalTime 的指定字段设置为新值，并返回新时间的副本。此方法可用于更改任何支持的字段，如小时、分钟或秒。如果由于字段不受支持或其他原因而无法设置新值，则会引发异常。LocalTime 的这个实例是不可变的，不受这个方法调用的影响。

**语法:**

```
public LocalTime with(TemporalField field, long newValue)

```

**参数:**此方法接受**字段**和**新值**，前者是要在结果中设置的字段，后者是结果中字段的新值作为参数。

**返回值:**该方法返回一个基于此的带有指定字段集的 LocalTime。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **unsupportedtemporaltypexception**–如果不支持该字段。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了用()方法:
**程序 1:**

```
// Java program to demonstrate
// LocalTime.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime local
            = LocalTime.parse(
                "13:12:23");

        // print instance
        System.out.println("LocalTime before"
                           + " applying method: "
                           + local);

        // apply with method of LocalTime class
        LocalTime updatedlocal
            = local.with(
                ChronoField.SECOND_OF_MINUTE, 55);

        // print instance
        System.out.println("LocalTime after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**Output:**

```
LocalTime before applying method: 13:12:23
LocalTime after applying method: 13:12:55

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # with(Java . time . temporal adjuster)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#with(java.time.temporal.TemporalAdjuster))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # with(Java . time . temporal field，long)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#with(java.time.temporal.TemporalField, long))