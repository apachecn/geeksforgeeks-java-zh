# Java 中持续时间毫秒(长)的方法，示例

> 原文:[https://www . geesforgeks . org/duration-minsmillislong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-minusmillislong-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的**毫秒(长)**方法用于获取该持续时间的不可变副本，减去指定的毫秒数，作为参数传递。

**语法:**

```
public Duration minusMillis(long numberOfMillis)
```

**参数:**该方法接受一个参数 **numberOfMillis** ，即需要减去的毫秒数。它可以是正数或负数，但不能为空。

**返回值:**该方法返回一个**持续时间**，它是一个不可变的现有持续时间的副本，参数值为毫秒。

**异常:**如果出现数值溢出，这个方法抛出**算法异常**。

以下示例说明了持续时间(毫秒)方法:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate minusMillis() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the duration subtracted
        // using minusMillis() method
        System.out.println(duration1.minusMillis(2));
    }
}
```

**Output:** 

```
PT51H3M59.998S
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate minusMillis() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P0DT0H4M");

        // Get the duration subtracted
        // using minusMillis() method
        System.out.println(duration1.minusMillis(5));
    }
}
```

**Output:** 

```
PT3M59.995S
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # mins millis-long-T4】