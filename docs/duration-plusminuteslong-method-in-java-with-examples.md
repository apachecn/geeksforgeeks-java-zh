# Java 中的 Duration plusMinutes(长)方法，示例

> 原文:[https://www . geesforgeks . org/duration-plusminutslong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-plusminuteslong-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的 **plusMinutes(long)** 方法用于获取该持续时间的不可变副本，并添加指定的分钟数，作为参数传递。

**语法:**

```java
public Duration plusMinutes(long numberOfMinutes)

```

**参数:**该方法接受一个参数**分钟数**，即需要添加的分钟数。它可以是正数或负数，但不能为空。

**返回值:**这个方法返回一个**持续时间**，它是一个不可变的现有持续时间的副本，参数分钟数被添加到其中。

**异常:**如果出现数值溢出，这个方法抛出**算法异常**。

以下示例说明了 Duration.plusMinutes()方法:

**例 1:**

```java
// Java code to illustrate plusMinutes() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the duration added
        // using plusMinutes() method
        System.out.println(duration1.plusMinutes(2));
    }
}
```

**输出:**

```java
PT51H6M

```

**例 2:**

```java
// Java code to illustrate plusMinutes() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P0DT0H4M");

        // Get the duration added
        // using plusMinutes() method
        System.out.println(duration1.plusMinutes(5));
    }
}
```

**输出:**

```java
PT9M

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # plusMinutes-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#plusMinutes-long-)