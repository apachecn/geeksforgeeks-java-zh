# Java 中的 Duration plus(Duration)方法，示例

> 原文:[https://www . geesforgeks . org/duration-plus duration-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-plusduration-method-in-java-with-examples/)

**java.time 包**中 **Duration 类**的 **plus(Duration)** 方法用于获取该 Duration 的不可变副本，并添加指定的 Duration，作为参数传递。

**语法:**

```java
public Duration plus(Duration duration)

```

**参数:**此方法接受一个参数**持续时间**，这是要添加的持续时间。它可以是正数或负数，但不能为空。

**返回值:**该方法返回一个**持续时间**，它是一个现有持续时间的不可变副本，并添加了持续时间的参数量。

**异常:**如果出现数值溢出，这个方法抛出**算法异常**。

以下示例说明了 Duration.plus()方法:

**例 1:**

```java
// Java code to illustrate plus() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Duration 2 using ofHours() method
        Duration duration2
            = Duration.ofHours(5);

        // Get the duration added
        // using plus() method
        System.out.println(duration1
                               .plus(duration2));
    }
}
```

**输出:**

```java
PT56H4M

```

**例 2:**

```java
// Java code to illustrate plus() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P0DT0H4M");

        // Duration 2 using ofHours() method
        Duration duration2
            = Duration.ofDays(5);

        // Get the duration added
        // using plus() method
        System.out.println(duration1
                               .plus(duration2));
    }
}
```

**输出:**

```java
PT120H4M

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # plus-Java . time . duration-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#plus-java.time.Duration-)