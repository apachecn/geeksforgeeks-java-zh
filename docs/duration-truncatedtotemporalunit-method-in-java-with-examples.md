# Java 中的持续时间截断到(临时时间)方法，示例

> 原文:[https://www . geeksforgeeks . org/duration-shoppettemporalunit-method in-Java-with-examples/](https://www.geeksforgeeks.org/duration-truncatedtotemporalunit-method-in-java-with-examples/)

使用 **java.time 包**中**持续时间类**的**截断到(时态)**方法，以指定的单位获取该持续时间的值。

**语法:**

```java
public Duration truncatedTo(TemporalUnit unit)

```

**参数:**该方法接受一个参数**单位**，该单位是该持续时间值要转换成的单位。

**返回值:**该方法返回一个**持续时间**，该值被截断为指定的单位。

**异常:**此方法抛出:

*   **Abnormal date and time** : If the unit is invalid.
*   不支持的 dtime type exception:哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟。

以下示例说明了 Duration .截断到()方法:

**例 1:**

```java
// Java code to illustrate truncatedTo() method

import java.time.Duration;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration
            = Duration.parse("P2DT3H4M");

        System.out.println("Original duration: "
                           + duration);

        // Truncate the duration to seconds
        // using truncatedTo() method
        System.out.println(
            duration
                .truncatedTo(ChronoUnit.SECONDS));
    }
}
```

**输出:**

```java
Original duration: PT51H4M
PT51H4M

```

**例 2:**

```java
// Java code to illustrate truncatedTo() method

import java.time.Duration;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Duration
        Duration duration
            = Duration.ofDays(5);

        System.out.println("Original duration: "
                           + duration);

        // Truncate the duration to nano-seconds
        // using truncatedTo() method
        System.out.println(
            duration
                .truncatedTo(ChronoUnit.NANOS));
    }
}
```

**输出:**

```java
Original duration: PT120H
PT120H

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html #截断 to-Java . time . temporal unit-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#truncatedTo-java.time.temporal.TemporalUnit-)