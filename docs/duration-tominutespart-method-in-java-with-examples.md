# Java 中的 Duration toMinutesPart()方法，示例

> 原文:[https://www . geeksforgeeks . org/duration-tominuespart-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-tominutespart-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的 **toMinutesPart()** 方法是用一小时内的分钟数除以分钟数得到这个持续时间的值。

**语法:**

```
public long toMinutesPart()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回一个**长值**，这个长值就是这个时长内的分钟数除以一小时内的分钟数。

以下示例说明了 Duration.toMinutesPart()方法:

**例 1:**

```
// Java code to illustrate toMinutesPart() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration
            = Duration.parse("P2DT3H4M");

        System.out.println("Duration: "
                           + duration);

        // Get the number of minutes
        // using toMinutesPart() method
        System.out.println(duration.toMinutesPart());
    }
}
```

**输出:**

```
Duration: PT51H4M
4

```

**例 2:**

```
// Java code to illustrate toMinutesPart() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofMinutes() method
        Duration duration
            = Duration.ofMinutes(10);

        System.out.println("Duration: "
                           + duration);

        // Get the number of minutes
        // using toMinutesPart() method
        System.out.println(duration.toMinutesPart());
    }
}
```

**输出:**

```
Duration: PT10M
10

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # tominuespart–](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toMinutesPart--)