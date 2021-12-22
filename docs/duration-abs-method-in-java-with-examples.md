# Java 中的 Duration abs()方法，示例

> 原文:[https://www . geesforgeks . org/duration-ABS-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-abs-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的 **abs()** 方法用来获取这个持续时间的一个不可变的副本，具有绝对持续时间。

**语法:**

```
public Duration abs()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回一个**持续时间**，该持续时间是现有持续时间的不可变副本，具有绝对持续时间。

**异常:**如果出现数值溢出，这个方法抛出**算法异常**。

以下示例说明了 Duration.abs()方法:

**例 1:**

```
// Java code to illustrate abs() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the duration abs using abs() method
        System.out.println(duration1.abs());
    }
}
```

**输出:**

```
PT51H4M

```

**例 2:**

```
// Java code to illustrate abs() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration
        Duration duration2
            = Duration.ofDays(-5);

        // Get the duration abs using abs() method
        System.out.println(duration2.abs());
    }
}
```

**输出:**

```
PT120H

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#abs--)