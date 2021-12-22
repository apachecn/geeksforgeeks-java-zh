# Java 中持续时间分钟(长)的方法，示例

> 原文:[https://www . geesforgeks . org/duration-mins minutes long-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-minusminuteslong-method-in-java-with-examples/)

**java.time 包**中 **Duration 类**的**minutes(long)**方法用于获取该持续时间的不可变副本，减去指定的分钟数，作为参数传递。
**语法:**

```java
public Duration minusMinutes(long numberOfMinutes)
```

**参数:**该方法接受一个参数**分钟数**，即要减去的分钟数。它可以是正数或负数，但不能为空。
**返回值:**该方法返回**持续时间**，该持续时间是现有持续时间的不可变副本，并减去参数分钟数。
**异常:**如果出现数值溢出，该方法抛出**算术异常**。
以下示例说明 Duration.minusMinutes()方法:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate minusMinutes() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the duration subtracted
        // using minusMinutes() method
        System.out.println(duration1.minusMinutes(2));
    }
}
```

**Output:** 

```java
PT51H2M
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate minusMinutes() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P0DT0H4M");

        // Get the duration subtracted
        // using minusMinutes() method
        System.out.println(duration1.minusMinutes(5));
    }
}
```

**Output:** 

```java
PT-1M
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # mins minutes-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#minusMinutes-long-)