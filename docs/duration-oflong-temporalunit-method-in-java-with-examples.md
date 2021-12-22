# Java 中(long，TemporalUnit)方法的持续时间，示例

> 原文:[https://www . geesforgeks . org/duration-of long-tempalalunit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-oflong-temporalunit-method-in-java-with-examples/)

**java.time 包**中 **Duration 类**的(long，TemporalUnit) 方法的**用于获取作为第一个参数传递的金额在作为第二个参数传递的 TemporalUnit 中的持续时间。时间单位可以是天、小时等。**

**语法:**

```
public static Duration of(long amount, TemporalUnit unit)

```

**参数:**此方法接受两个参数:

*   **Amount** : that is, the number of seconds. It can be positive or negative.
*   **Unit** : It is the time unit of the specified unit.

**返回值:**该方法返回一个以指定单位格式表示时间的**持续时间**。

**异常:**此方法抛出以下单位:

*   **Arithmetic exception** : If the input number of seconds exceeds the capacity of the duration.
*   **Abnormal date and time** : If the period unit has an estimated duration.

以下示例说明了()方法的持续时间:

**例 1:**

```
// Java code to illustrate of() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // input amount of time
        long timeAmount = 5;

        // Duration using of() method
        Duration duration
            = Duration.of(timeAmount, ChronoUnit.DAYS);

        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```
432000

```

**例 2:**

```
// Java code to illustrate of() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // input amount of time
        long timeAmount = 5;

        // Duration using of() method
        Duration duration
            = Duration.of(timeAmount, ChronoUnit.HOURS);

        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```
18000

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # of-long-Java . time . temporalunit-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#of-long-java.time.temporal.TemporalUnit-)