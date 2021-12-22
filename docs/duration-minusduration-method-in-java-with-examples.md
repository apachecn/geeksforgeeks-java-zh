# Java 中的 Duration 减(Duration)方法，示例

> 原文:[https://www . geesforgeks . org/duration-minusduration-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-minusduration-method-in-java-with-examples/)

**java.time 包**中 **Duration 类**的**减(Duration)** 方法用于获取这个 Duration 的不可变副本，减去指定的 Duration，作为参数传递。
**语法:**

```java
public Duration minus(Duration duration)
```

**参数:**该方法接受一个参数**持续时间**，即要减去的持续时间。它可以是正数或负数，但不能为空。
**返回值:**该方法返回**持续时间**，该持续时间是现有持续时间的不可变副本，并减去持续时间的参数量。
**异常:**如果出现数值溢出，该方法抛出**算术异常**。
以下示例说明了 Duration .减()方法:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate minus() method

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

        // Get the duration subtracted
        // using minus() method
        System.out.println(duration1
                               .minus(duration2));
    }
}
```

**Output:** 

```java
PT46H4M
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate minus() method

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

        // Get the duration subtracted
        // using minus() method
        System.out.println(duration1
                               .minus(duration2));
    }
}
```

**Output:** 

```java
PT-119H-56M
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html #减-Java . time . duration-T4】