# Java 中的 Duration toMinutes()方法，示例

> 原文:[https://www . geeksforgeeks . org/duration-tomi nutes-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-tominutes-method-in-java-with-examples/)

使用 **java.time 包**中**持续时间类**的 **toMinutes()** 方法获取该持续时间的分钟值。

**语法:**

```
public long toMinutes()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回一个**长值**，即该时长内的分钟数。

以下示例说明了 Duration.toMinutes()方法:

**例 1:**

```
// Java code to illustrate toMinutes() method

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
        // using toMinutes() method
        System.out.println(duration.toMinutes());
    }
}
```

**输出:**

```
Duration: PT51H4M
3064

```

**例 2:**

```
// Java code to illustrate toMinutes() method

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
        // using toMinutes() method
        System.out.println(duration.toMinutes());
    }
}
```

**输出:**

```
Duration: PT10M
10

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # toMinutes–](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toMinutes--)