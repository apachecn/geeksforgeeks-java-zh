# Java 中的 Duration toDays()方法，示例

> 原文:[https://www . geesforgeks . org/duration-today-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-todays-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的**Today()**方法用于获取该持续时间的天数值。

**语法:**

```
public long toDays()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回一个**长值**，即该时长内的天数。

下面的例子说明了 Duration.toDays()方法:

**例 1:**

```
// Java code to illustrate toDays() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration
            = Duration.parse("P2DT3H4M");

        System.out.println("Duration: "
                           + duration);

        // Get the number of days
        // using toDays() method
        System.out.println(duration.toDays());
    }
}
```

**输出:**

```
Duration: PT51H4M
2

```

**例 2:**

```
// Java code to illustrate toDays() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofDays() method
        Duration duration
            = Duration.ofDays(10);

        System.out.println("Duration: "
                           + duration);

        // Get the number of days
        // using toDays() method
        System.out.println(duration.toDays());
    }
}
```

**输出:**

```
Duration: PT240H
10

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # Todays–](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toDays--)