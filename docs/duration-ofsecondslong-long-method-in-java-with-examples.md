# Java 中秒(长，长)方法的持续时间举例

> 原文:[https://www . geesforgeks . org/duration-of seconds long-long-in-Java-method-with-examples/](https://www.geeksforgeeks.org/duration-ofsecondslong-long-method-in-java-with-examples/)

**java.time 包**中**时长类**的 **ofSeconds(长，长)**方法用于获取 1 秒格式的时长。在这种方法中，秒以 1 秒的格式(即每秒 1 秒)计算为总秒。第二个参数 nanoAdjustment 用于以纳秒为单位调整秒。

**语法:**

```
public static Duration ofSeconds(long seconds, long nanoAdjustment)

```

**参数:**这个方法接受两个参数:

*   **Seconds** : That is, seconds. It can be positive or negative.
*   **nano adjustment** : the adjustment to be made in seconds.

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
        long noOfSeconds = 214545;

        // input nanoSeconds adjustment to be made
        long nanoSecAdjust = 10000;

        // Duration using ofSeconds() method
        Duration duration
            = Duration.ofSeconds(noOfSeconds);
        Duration duration1
            = Duration.ofSeconds(noOfSeconds,
                                 nanoSecAdjust);

        System.out.println("Duration without adjustment: "
                           + duration.getSeconds());
        System.out.println("Duration with adjustment: "
                           + duration1.getSeconds());
    }
}
```

**输出:**

```
Duration without adjustment: 214545
Duration with adjustment: 214545

```

**例 2:**

```
// Java code to illustrate ofSeconds() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Seconds
        long noOfSeconds = 214545;

        // input nanoSeconds adjustment to be made
        long nanoSecAdjust = -10000;

        // Duration using ofSeconds() method
        Duration duration
            = Duration.ofSeconds(noOfSeconds);
        Duration duration1
            = Duration.ofSeconds(noOfSeconds,
                                 nanoSecAdjust);

        System.out.println("Duration without adjustment: "
                           + duration.getSeconds());
        System.out.println("Duration with adjustment: "
                           + duration1.getSeconds());
    }
}
```

**输出:**

```
Duration without adjustment: 214545
Duration with adjustment: 214544

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # of seconds-long-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#ofSeconds-long-long-)