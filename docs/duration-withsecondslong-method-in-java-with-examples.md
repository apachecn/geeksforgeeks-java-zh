# 持续时间为秒(长)的 Java 方法，示例

> 原文:[https://www . geesforgeks . org/duration-with second slong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-withsecondslong-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的 **withSeconds(长)**方法用于获取该持续时间的不可变副本，指定的秒数作为参数传递。

**语法:**

```java
public Duration withSeconds(long amountOfSeconds)

```

**参数:**该方法接受一个参数**秒量**，即秒量。

**返回值:**该方法返回一个作为参数传递的**持续时间**。

以下示例说明了 Duration.withSeconds()方法:

**例 1:**

```java
// Java code to illustrate withSeconds() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Get the amount of seconds
        long amountOfSeconds = 300;

        // Duration using parse() method
        Duration duration
            = Duration.parse("P2DT3H4M");

        // Get the duration in seconds
        // using withSeconds() method
        System.out.println(duration
                               .withSeconds(amountOfSeconds));
    }
}
```

**输出:**

```java
PT5M

```

**例 2:**

```java
// Java code to illustrate withSeconds() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Get the amount of seconds
        long amountOfSeconds = 3000;

        // Duration using ofHours() method
        Duration duration
            = Duration.ofHours(5);

        // Get the duration in seconds
        // using withSeconds() method
        System.out.println(duration
                               .withSeconds(amountOfSeconds));
    }
}
```

**输出:**

```java
PT50M

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # with seconds-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#withSeconds-long-)