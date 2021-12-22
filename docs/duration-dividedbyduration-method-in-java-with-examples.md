# Java 中的 Duration dividedBy(Duration)方法，示例

> 原文:[https://www . geesforgeks . org/duration-divided by duration-in-Java-method-with-examples/](https://www.geeksforgeeks.org/duration-dividedbyduration-method-in-java-with-examples/)

**java.time 包**中 **Duration 类**的 **dividedBy(Duration)** 方法用于获取这个 Duration 除以作为参数传递的 Duration 的不可变副本。

**语法:**

```java
public Duration dividedBy(Duration divisor)

```

**参数:**该方法接受一个参数**除数**，即待除的持续时间。它可以是正的或负的持续时间。

**返回值:**该方法返回一个**持续时间**，它是一个不可变的现有持续时间的副本，参数持续时间除以它。

**异常:**如果出现数值溢出，这个方法抛出**算法异常**。

以下示例说明了 Duration.dividedBy()方法:

**例 1:**

```java
// Java code to illustrate dividedBy() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Duration 2 as the divisor
        Duration duration2
            = Duration.ofHours(5);

        // Get the duration divided
        // using dividedBy() method
        System.out.println(
            duration1
                .dividedBy(duration2));
    }
}
```

**输出:**

```java
10

```

**例 2:**

```java
// Java code to illustrate dividedBy() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Duration 2 as the divisor
        Duration duration2
            = Duration.ofDays(5);

        // Get the duration divided
        // using dividedBy() method
        System.out.println(
            duration1
                .dividedBy(duration2));
    }
}
```

**输出:**

```java
0

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#dividedBy-java.time.Duration-)