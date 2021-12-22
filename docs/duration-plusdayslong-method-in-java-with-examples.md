# Java 中的 Duration plusDays(长)方法，示例

> 原文:[https://www . geesforgeks . org/duration-plusdayslong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-plusdayslong-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的 **plusDays(long)** 方法用于获取该持续时间的不可变副本，并添加指定的天数，作为参数传递。

**语法:**

```java
public Duration plusDays(long numberOfDays)

```

**参数:**该方法接受一个参数**天数**，即需要增加的天数。它可以是正数或负数，但不能为空。

**返回值:**该方法返回一个**持续时间**，该持续时间是一个不可变的现有持续时间的副本，其中添加了参数天数。

**异常:**如果出现数值溢出，这个方法抛出**算法异常**。

以下示例说明了 Duration.plusDays()方法:

**例 1:**

```java
// Java code to illustrate plusDays() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the duration added
        // using plusDays() method
        System.out.println(duration1.plusDays(2));
    }
}
```

**输出:**

```java
PT99H4M

```

**例 2:**

```java
// Java code to illustrate plusDays() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P0DT0H4M");

        // Get the duration added
        // using plusDays() method
        System.out.println(duration1.plusDays(5));
    }
}
```

**输出:**

```java
PT120H4M

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # plusDays-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#plusDays-long-)