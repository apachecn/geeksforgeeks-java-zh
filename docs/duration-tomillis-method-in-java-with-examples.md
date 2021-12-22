# Java 中 Duration toMillis()方法，示例

> 原文:[https://www . geesforgeks . org/duration-tomi llis-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-tomillis-method-in-java-with-examples/)

使用 **java.time 包**中**持续时间类**的**Tomilis()**方法获取该持续时间的值，单位为毫秒。

**语法:**

```
public long toMillis()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回一个**长值**，即该时长内的毫秒数。

以下示例说明了 Duration.toMillis()方法:

**例 1:**

```
// Java code to illustrate toMillis() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration
            = Duration.parse("P2DT3H4M");

        System.out.println("Duration: "
                           + duration);

        // Get the number of milli-seconds
        // using toMillis() method
        System.out.println(duration.toMillis());
    }
}
```

**输出:**

```
Duration: PT51H4M
183840000

```

**例 2:**

```
// Java code to illustrate toMillis() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofMillis() method
        Duration duration
            = Duration.ofMillis(10);

        System.out.println("Duration: "
                           + duration);

        // Get the number of milli-seconds
        // using toMillis() method
        System.out.println(duration.toMillis());
    }
}
```

**输出:**

```
Duration: PT0.01S
10

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # tomilis–](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toMillis--)