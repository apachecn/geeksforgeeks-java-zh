# Java 中的 Duration plusNanos(long)方法，示例

> 原文:[https://www . geesforgeks . org/duration-plusnanoslong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-plusnanoslong-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的 **plusNanos(long)** 方法用于获取该持续时间的不可变副本，并添加指定数量的纳米秒，作为参数传递。

**语法:**

```
public Duration plusNanos(long numberOfNanos)

```

**参数:**该方法接受一个参数**数**，即需要相加的纳秒数。它可以是正数或负数，但不能为空。

**返回值:**该方法返回一个**持续时间**，该持续时间是一个不可变的现有持续时间的副本，添加了纳米秒的参数量。

**异常:**如果出现数值溢出，这个方法抛出**算法异常**。

以下示例说明了 Duration.plusNanos()方法:

**例 1:**

```
// Java code to illustrate plusNanos() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the duration added
        // using plusNanos() method
        System.out.println(duration1.plusNanos(2));
    }
}
```

**输出:**

```
PT51H4M0.000000002S

```

**例 2:**

```
// Java code to illustrate plusNanos() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P0DT0H4M");

        // Get the duration added
        // using plusNanos() method
        System.out.println(duration1.plusNanos(5));
    }
}
```

**输出:**

```
PT4M0.000000005S

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # plusNanos-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#plusNanos-long-)