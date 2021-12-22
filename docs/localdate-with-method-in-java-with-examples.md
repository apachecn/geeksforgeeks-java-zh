# Java 中带有()方法的 LocalDate，示例

> 原文:[https://www . geesforgeks . org/local date-with-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-with-method-in-java-with-examples/)

在 LocalDate 类中，根据传递给它的参数，有两种类型的 with()方法。

### 带(临时调节器)

**用 **LocalDate** 类的(临时调整者)**方法，使用作为参数传递的临时调整者来调整该日期时间，调整后返回调整后的日期时间的副本。使用指定的调整器策略对象进行调整。LocalDate 的这个实例是不可变的，不受这个方法调用的影响。

**语法:**

```java
public LocalDate with(TemporalAdjuster adjuster)

```

**参数:**该方法接受**调节器**作为参数，调节器使用该参数。

**返回值:**该方法根据调整后的值返回一个本地日期。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了 with()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalDate.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate local
            = LocalDate.parse(
                "2018-12-06");

        // print instance
        System.out.println("LocalDate before"
                           + " adjustment: "
                           + local);

        // apply with method of LocalDate class
        LocalDate updatedlocal
            = local.with(Month.MARCH)
                  .with(TemporalAdjusters
                            .lastDayOfMonth());

        // print instance
        System.out.println("LocalDate after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

**Output:**

```java
LocalDate before adjustment: 2018-12-06
LocalDate after adjustment: 2018-03-31

```

### 带(临时字段，长新值)

**使用 **LocalDate** 类的(临时字段，长 newValue)** 方法，用于将 LocalDate 的指定字段设置为新值，并返回新日期时间的副本。此方法可用于更改任何受支持的字段，如年、月或月中的某一天。如果由于字段不受支持或其他原因而无法设置新值，则会引发异常。
在某些情况下，更改指定的字段会导致结果日期时间无效，例如将月份从 1 月 31 日更改为 2 月会使当月的某一天无效。在这种情况下，字段负责解析日期。通常，它会选择以前的有效日期，在本例中是二月的最后一个有效日期。LocalDate 的这个实例是不可变的，不受这个方法调用的影响。

**语法:**

```java
public LocalDate with(TemporalField field, long newValue)

```

**参数:**此方法接受**字段**和**新值**，前者是要在结果中设置的字段，后者是结果中字段的新值作为参数。

**返回值:**该方法基于此返回一个带有指定字段集的 LocalDate。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **unsupportedtemporaltypexception**–如果不支持该字段。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了 with()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalDate.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate local
            = LocalDate.parse(
                "2018-12-06");

        // print instance
        System.out.println("LocalDate before"
                           + " applying method: "
                           + local);

        // apply with method of LocalDate class
        LocalDate updatedlocal
            = local.with(
                ChronoField.DAY_OF_MONTH, 30);

        // print instance
        System.out.println("LocalDate after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**Output:**

```java
LocalDate before applying method: 2018-12-06
LocalDate after applying method: 2018-12-30

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # with(Java . time . temporal field，long)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#with(java.time.temporal.TemporalField, long))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # with(Java . time . temporal adjuster)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#with(java.time.temporal.TemporalAdjuster))