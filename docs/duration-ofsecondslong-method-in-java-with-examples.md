# Java 中秒(长)的持续时间方法，示例

> 原文:[https://www . geesforgeks . org/duration-of seconds long-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-ofsecondslong-method-in-java-with-examples/)

**java.time 包**中**时长类**的 **ofSeconds(长)**方法用于获取 1 秒格式的时长。在这种方法中，秒以 1 秒的格式(即每秒 1 秒)计算为总秒。

**语法:**

```
public static Duration ofSeconds(long seconds)

```

**参数:**该方法接受一个参数**秒**，即秒数。它可以是积极的，也可以是消极的。

**返回值:**该方法返回一个**持续时间**，以 1 秒的格式表示时间。

**异常:**如果输入秒数超过持续时间的容量，该方法抛出**算法异常**。

以下示例说明了持续时间秒()方法:

**例 1:**

```
// Java code to illustrate ofSeconds() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Seconds
        long noOfSeconds = 5;

        // Duration using ofSeconds() method
        Duration duration
            = Duration.ofSeconds(noOfSeconds);

        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```
5

```

**例 2:**

```
// Java code to illustrate ofSeconds() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Seconds
        long noOfSeconds = -214545;

        // Duration using ofSeconds() method
        Duration duration
            = Duration.ofSeconds(noOfSeconds);

        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```
-214545

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # of seconds-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#ofSeconds-long-)