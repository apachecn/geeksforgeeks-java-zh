# Java 中的持续时间获取方法，示例

> 原文:[https://www . geesforgeks . org/duration-gettemporalunit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-gettemporalunit-method-in-java-with-examples/)

**java.time 包**中 **Duration 类**的 **get(TemporalUnit)** 方法用于获取作为参数传递的单位值。该方法仅支持单位秒和纳米，其余均导致异常。

**语法:**

```java
public long get(TemporalUnit unit)

```

**参数:**该方法接受一个参数**单位**，该单位是要获取其值的时间单位。

**返回值:**该方法返回作为参数传递的单位的一个**长值**。

**异常:**此方法抛出:

*   **Abnormal date and time** : If the company is not supported.
*   不支持的 dtime type exception:哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟。

下面的例子说明了 Duration.get()方法:

**例 1:**

```java
// Java code to illustrate get() method

import java.time.Duration;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the text
        String time = "P2DT3H4M";

        // Duration using parse() method
        Duration duration = Duration.parse(time);

        // Duration using get() method
        long getSeconds
            = duration.get(ChronoUnit.SECONDS);

        System.out.println("Seconds: "
                           + getSeconds);

        // Duration using get() method
        long getNanos
            = duration.get(ChronoUnit.NANOS);

        System.out.println("Nanos: "
                           + getNanos);
    }
}
```

**输出:**

```java
Seconds: 183840
Nanos: 0

```

**例 2:**

```java
// Java code to illustrate get() method

import java.time.Duration;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the text
        String time = "P2DT3H4M";

        // Duration using parse() method
        Duration duration
            = Duration.parse(time);

        try {
            // Duration using get() method
            long getMinutes
                = duration.get(ChronoUnit.MINUTES);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
Exception:
 java.time.temporal.UnsupportedTemporalTypeException:
 Unsupported unit: Minutes

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#get-java.time.temporal.TemporalUnit-)