# Java 中的持续时间(长)方法，示例

> 原文:[https://www . geesforgeks . org/duration-of nanoslong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-ofnanoslong-method-in-java-with-examples/)

**java.time 包**中**时长类**的 **ofNanos(long)** 方法用于获取 1 纳秒格式的时长。

**语法:**

```java
public static Duration ofNanos(long nanoSeconds)

```

**参数:**该方法接受一个参数**纳秒**，即纳秒数。它可以是积极的，也可以是消极的。

**返回值:**该方法返回一个**持续时间**，以 1 纳秒的格式表示时间。

**异常:**如果输入纳秒超过持续时间的容量，该方法抛出**算法异常**。

以下示例说明了持续时间()方法:

**例 1:**

```java
// Java code to illustrate ofNanos() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Nanos
        long noOfNanos = 1000000;

        // Duration using ofNanos() method
        Duration duration
            = Duration.ofNanos(noOfNanos);

        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```java
0

```

**例 2:**

```java
// Java code to illustrate ofNanos() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Nanos
        long noOfNanos = -1000000;

        // Duration using ofNanos() method
        Duration duration
            = Duration.ofNanos(noOfNanos);

        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```java
-1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # ofNanos-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#ofNanos-long-)