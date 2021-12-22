# Java 中的 Duration toSecondsPart()方法，示例

> 原文:[https://www . geesforgeks . org/duration-to secondspart-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-tosecondspart-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的**到秒间隔()**方法用于通过除以一分钟的秒数得到该持续时间的值。

**语法:**

```
public long toSecondsPart()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回一个**长值**，这个长值是这个持续时间内的秒数除以一分钟的秒数。

以下示例说明了 Duration.toSecondsPart()方法:

**例 1:**

```
// Java code to illustrate toSecondsPart() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration = Duration.parse("P2DT3H4M");

        System.out.println("Duration: "
                           + duration);

        // Get the number of seconds
        // using toSecondsPart() method
        System.out.println(duration.toSecondsPart());
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
// Java code to illustrate toSecondsPart() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofSeconds() method
        Duration duration
            = Duration.ofSeconds(10);

        System.out.println("Duration: "
                           + duration);

        // Get the number of seconds
        // using toSecondsPart() method
        System.out.println(duration.toSecondsPart());
    }
}
```

**输出:**

```
Duration: PT10S
10

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # to secondspart–](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toSecondsPart--)