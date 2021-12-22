# Java 中的持续时间加秒(长)方法，示例

> 原文:[https://www . geesforgeks . org/duration-plussecondslong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-plussecondslong-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的 **plusSeconds(long)** 方法用于获取该持续时间的不可变副本，并添加指定的秒数，作为参数传递。

**语法:**

```java
public Duration plusSeconds(long numberOfSeconds)

```

**参数:**该方法接受一个参数**秒数**，这是要添加的秒数。它可以是正数或负数，但不能为空。

**返回值:**该方法返回一个**持续时间**，该持续时间是一个不可变的现有持续时间的副本，并添加了参数秒数。

**异常:**如果出现数值溢出，这个方法抛出**算法异常**。

以下示例说明了 Duration.plusSeconds()方法:

**例 1:**

```java
// Java code to illustrate plusSeconds() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the duration added
        // using plusSeconds() method
        System.out.println(duration1.plusSeconds(2));
    }
}
```

**输出:**

```java
PT51H4M2S

```

**例 2:**

```java
// Java code to illustrate plusSeconds() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P0DT0H4M");

        // Get the duration added
        // using plusSeconds() method
        System.out.println(duration1.plusSeconds(5));
    }
}
```

**输出:**

```java
PT4M5S

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # plus seconds-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#plusSeconds-long-)