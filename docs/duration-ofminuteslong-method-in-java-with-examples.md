# Java 中的分钟(长)持续时间方法，示例

> 原文:[https://www . geesforgeks . org/duration-of minuteslong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-ofminuteslong-method-in-java-with-examples/)

**java.time 包**中**时长类**的**分钟(长)**方法用于获取 1 分钟格式的时长。在这种方法中，秒以 1 分钟格式的总秒计算，即每分钟 60 秒。

**语法:**

```
public static Duration ofMinutes(long minutes)

```

**参数:**该方法接受一个参数**分钟**，即分钟数。它可以是积极的，也可以是消极的。

**返回值:**该方法返回一个**持续时间**，以 1 分钟的格式表示时间。

**异常:**如果输入分钟数超过持续时间的容量，该方法抛出**算法异常**。

以下示例说明了 Duration.ofMinutes()方法:

**例 1:**

```
// Java code to illustrate ofMinutes() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Minutes
        long noOfMinutes = 5;

        // Duration using ofMinutes() method
        Duration duration
            = Duration.ofMinutes(noOfMinutes);

        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```
300

```

**例 2:**

```
// Java code to illustrate ofMinutes() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Minutes
        long noOfMinutes = -214545;

        // Duration using ofMinutes() method
        Duration duration
            = Duration.ofMinutes(noOfMinutes);

        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```
-12872700

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # of minutes-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#ofMinutes-long-)