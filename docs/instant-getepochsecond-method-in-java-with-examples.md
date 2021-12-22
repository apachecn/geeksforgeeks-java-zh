# Java 中的 Instant getEpochSecond()方法，示例

> 原文:[https://www . geeksforgeeks . org/instant-getepochsecond-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-getepochsecond-method-in-java-with-examples/)

Instant 类的 **getEpochSecond()** 方法用于返回从 1970-01-01T00:00:00Z 的 Java 纪元开始的秒数。这意味着此实例的时间(以秒为单位)与“1970-01-01T00:00:00Z”所表示的时间之间的差异通过此方法返回。历元秒计数是简单的递增秒计数，其中秒 0 是 1970-01-01T00:00:00Z。

**语法:**

```
public long getEpochSecond()
```

**返回:**该方法返回 1970-01-01T00:00:00Z 的**秒**。

下面的程序说明了 Instant.getEpochSecond()方法:

**程序 1:**

```
// Java program to demonstrate
// Instant.getEpochSecond() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create  instance object
        Instant instant
            = Instant.parse("2018-10-20T16:55:30.00Z");

        // print Instant Value
        System.out.println("Instant: " + instant);

        // get epochValue using getEpochSecond
        long epochValue = instant.getEpochSecond();

        // print results
        System.out.println("Java epoch Value: "
                           + epochValue);
    }
}
```

**输出:**

```
Instant: 2018-10-20T16:55:30Z
Java epoch Value: 1540054530

```

**程序二:**

```
// Java program to demonstrate
// Instant.getEpochSecond() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create current instance object
        Instant instant
            = Instant.now();

        // print Instant Value
        System.out.println("Current Instant: "
                           + instant);

        // get epochValue using getEpochSecond
        long epochValue = instant.getEpochSecond();

        // print results
        System.out.println("Java epoch Value: "
                           + epochValue);
    }
}
```

**输出:**

```
Current Instant: 2018-11-22T08:26:19.502Z
Java epoch Value: 1542875179

```

参考:[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # getEpochSecond()](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#getEpochSecond())