# Java 中的时长除以(长)方法，示例

> 原文:[https://www . geesforgeks . org/duration-divided bylong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-dividedbylong-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的 **dividedBy(long)** 方法用于获取该持续时间除以作为参数传递的值的不可变副本。

**语法:**

```java
public Duration dividedBy(long divisor)

```

**参数:**该方法接受一个参数**除数**，即待除的值。它可以是正值或负值。

**返回值:**该方法返回一个**持续时间**，它是一个不可变的现有持续时间的副本，参数值除以它。

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

        // divisor value
        long divisor = 2;

        // Get the duration divided
        // using dividedBy() method
        System.out.println(duration1
                               .dividedBy(divisor));
    }
}
```

**输出:**

```java
PT25H32M

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

        // divisor value
        long divisor = 10;

        // Get the duration divided
        // using dividedBy() method
        System.out.println(duration1
                               .dividedBy(divisor));
    }
}
```

**输出:**

```java
PT5H6M24S

```

[**参考:**](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#dividedBy-long-) 甲骨文文档