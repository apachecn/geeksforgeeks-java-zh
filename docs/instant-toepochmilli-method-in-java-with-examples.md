# Java 中的 Instant toEpochMilli()方法，带示例

> 原文:[https://www . geesforgeks . org/instant-toepchmilli-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-toepochmilli-method-in-java-with-examples/)

一个**即时类**的**to pochmilli()**方法用于将这个瞬间转换为从 1970-01-01T00:00:00Z 的历元到长值的毫秒数。这个方法返回那个长值。
**语法:**

```java
public long toEpochMilli()
```

**返回:**此方法返回自 1970-01-01T00:00:00Z 纪元以来的**毫秒数**。
**异常:**如果出现数值溢出，这个方法抛出**算术异常**。
以下程序说明了 Instant.toEpochMilli()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Instant.toEpochMilli() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // get millisecond value using toEpochMilli()
        long value = instant.toEpochMilli();

        // print result
        System.out.println("Millisecond value: "
                           + value);
    }
}
```

![](img/042dbb230dbb2e9d4a7420975066b9cd.png)

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Instant.toEpochMilli() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant = Instant.now();

        // current Instant
        System.out.println("Current Instant: "
                           + instant);

        // get millisecond value using toEpochMilli()
        long value = instant.toEpochMilli();

        // print result
        System.out.println("Millisecond value: "
                           + value);
    }
}
```

![](img/d127c41fdd848880375224fdaeeceba0.png)

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/Instant . html # Toepochmilli()](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#toEpochMilli())