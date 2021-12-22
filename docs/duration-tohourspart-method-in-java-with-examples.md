# Java 中的 Duration toHoursPart()方法，示例

> 原文:[https://www . geesforgeks . org/duration-to ourspart-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-tohourspart-method-in-java-with-examples/)

**java.time 包**中**时长类**的 **toHoursPart()** 方法用于通过除以一天的小时数得到该时长的小时数值。

**语法:**

```java
public long toHoursPart()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回一个**长值**，这个长值就是这个持续时间内的小时数除以一天的小时数。

以下示例说明了 duration . to ourspart()方法:

**例 1:**

```java
// Java code to illustrate toHoursPart() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration
            = Duration.parse("P2DT3H4M");

        System.out.println("Duration: "
                           + duration);

        // Get the number of hours
        // using toHoursPart() method
        System.out.println(duration.toHoursPart());
    }
}
```

**输出:**

```java
Duration: PT51H4M
3

```

**例 2:**

```java
// Java code to illustrate toHoursPart() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofHours() method
        Duration duration
            = Duration.ofHours(10);

        System.out.println("Duration: "
                           + duration);

        // Get the number of hours
        // using toHoursPart() method
        System.out.println(duration.toHoursPart());
    }
}
```

**输出:**

```java
Duration: PT10H
10

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # to ourspart–](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toHoursPart--)