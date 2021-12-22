# Java 中持续时间不稳定(长)的方法，示例

> 原文:[https://www . geesforgeks . org/duration-minsecondslong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-minussecondslong-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的**不变秒(长)**方法用于获取该持续时间的不变副本，减去指定的秒数，作为参数传递。

**语法:**

```java
public Duration minusSeconds(long numberOfSeconds)

```

**参数:**该方法接受一个参数**秒数**，这是要减去的秒数。它可以是正数或负数，但不能为空。

**返回值:**该方法返回一个**持续时间**，它是一个现有持续时间的不可变副本，并减去了参数秒数。

**异常:**如果出现数值溢出，这个方法抛出**算法异常**。

下面的例子说明了 Duration.minusSeconds()方法:

**例 1:**

```java
// Java code to illustrate minusSeconds() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the duration subtracted
        // using minusSeconds() method
        System.out.println(duration1.minusSeconds(2));
    }
}
```

**输出:**

```java
PT51H3M58S

```

**例 2:**

```java
// Java code to illustrate minusSeconds() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P0DT0H4M");

        // Get the duration subtracted
        // using minusSeconds() method
        System.out.println(duration1.minusSeconds(5));
    }
}
```

**输出:**

```java
PT3M55S

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # mins seconds-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#minusSeconds-long-)