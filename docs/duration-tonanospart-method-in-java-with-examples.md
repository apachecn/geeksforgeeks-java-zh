# Java 中的 Duration toNanosPart()方法，带示例

> 原文:[https://www . geesforgeks . org/duration-tonanopart-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-tonanospart-method-in-java-with-examples/)

**java.time 包**中**时长类**的**tonanopart()**方法用于获取时长秒内的纳秒部分。

**语法:**

```
public long toNanosPart()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回一个**长值**，即持续时间秒内的纳秒部分。

以下示例说明了 Duration.toNanosPart()方法:

**例 1:**

```
// Java code to illustrate toNanosPart() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration
            = Duration.parse("P2DT3H4M");

        System.out.println("Duration: "
                           + duration);

        // Get the number of nano-seconds
        // using toNanosPart() method
        System.out.println(duration.toNanosPart());
    }
}
```

**输出:**

```
Duration: PT51H4M
0

```

**例 2:**

```
// Java code to illustrate toNanosPart() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofNanos() method
        Duration duration = Duration.ofNanos(10);

        System.out.println("Duration: "
                           + duration);

        // Get the number of nano-seconds
        // using toNanosPart() method
        System.out.println(duration.toNanosPart());
    }
}
```

**输出:**

```
Duration: PT0.00000001S
10

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # tonanopart–](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toNanosPart--)