# Java 中的 Duration toNanos()方法，示例

> 原文:[https://www . geesforgeks . org/duration-tonanos-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-tonanos-method-in-java-with-examples/)

使用 **java.time 包**中**持续时间类**的 **toNanos()** 方法获取该持续时间的值，单位为纳米秒。

**语法:**

```
public long toNanos()

```

**参数:**该方法不接受任何参数。

**返回值:**此方法返回一个**长值**，即此时长内的纳秒数。

以下示例说明了 Duration.toNanos()方法:

**例 1:**

```
// Java code to illustrate toNanos() method

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
        // using toNanos() method
        System.out.println(duration.toNanos());
    }
}
```

**输出:**

```
Duration: PT51H4M
183840000000000

```

**例 2:**

```
// Java code to illustrate toNanos() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofNanos() method
        Duration duration
            = Duration.ofNanos(10);

        System.out.println("Duration: "
                           + duration);

        // Get the number of nano-seconds
        // using toNanos() method
        System.out.println(duration.toNanos());
    }
}
```

**输出:**

```
Duration: PT0.00000001S
10

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # toNanos–](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toNanos--)