# Java 中持续天数(长)方法，示例

> 原文:[https://www . geesforgeks . org/duration-of dayslong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-ofdayslong-method-in-java-with-examples/)

**java.time 包**中**时长类**的**天数(长)**方法用于获取 24 小时格式的时长。在这种方法中，秒以 24 小时制的总秒计算，即每天 86400 秒。

**语法:**

```
public static Duration ofDays(long days)

```

**参数:**该方法接受一个参数**天数**，即天数。它可以是积极的，也可以是消极的。

**返回值:**该方法返回一个**持续时间**，代表 24 小时格式的时间。

**异常:**如果输入天数超过持续时间的容量，该方法抛出**算法异常**。

以下示例说明了 Duration.ofDays()方法:

**例 1:**

```
// Java code to illustrate ofDays() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Days
        long noOfDays = 5;

        // Duration using ofDays() method
        Duration duration = Duration.ofDays(noOfDays);

        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```
432000

```

**例 2:**

```
// Java code to illustrate ofDays() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Days
        long noOfDays = -214545;

        // Duration using ofDays() method
        Duration duration = Duration.ofDays(noOfDays);

        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```
-18536688000

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # of days-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#ofDays-long-)