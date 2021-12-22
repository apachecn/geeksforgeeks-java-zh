# Java 中用(长)方法相乘的持续时间，示例

> 原文:[https://www . geesforgeks . org/duration-multipliedbylong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-multipliedbylong-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的**乘以(长)**方法用于获得该持续时间乘以作为参数传递的值的不可变副本。

**语法:**

```java
public Duration multipliedBy(long multiplicand)

```

**参数:**该方法接受一个参数**被乘数**，即需要相乘的值。它可以是正值或负值。

**返回值:**这个方法返回一个**持续时间**，它是一个不可变的现有持续时间的副本，参数值乘以它。

**异常:**如果出现数值溢出，这个方法抛出**算法异常**。

以下示例说明了 Duration.multipliedBy()方法:

**例 1:**

```java
// Java code to illustrate multipliedBy() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // multiplicand value
        long multiplicand = 2;

        // Get the duration multiplied
        // using multipliedBy() method
        System.out.println(duration1
                               .multipliedBy(multiplicand));
    }
}
```

**输出:**

```java
PT102H8M

```

**例 2:**

```java
// Java code to illustrate multipliedBy() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // multiplicand value
        long multiplicand = 10;

        // Get the duration multiplied
        // using multipliedBy() method
        System.out.println(duration1
                               .multipliedBy(multiplicand));
    }
}
```

**输出:**

```java
PT510H40M

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html #乘法 By-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#multipliedBy-long-)