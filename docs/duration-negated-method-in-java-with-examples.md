# Java 中的持续时间求反()方法，示例

> 原文:[https://www . geeksforgeeks . org/duration-invalid-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-negated-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的**求反()**方法用于获取持续时间被求反的该持续时间的不可变副本。

**语法:**

```
public Duration negated()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回一个**持续时间**，它是一个不可变的现有持续时间的副本，持续时间被否定。

**异常:**如果出现数值溢出，这个方法抛出**算法异常**。

以下示例说明了 Duration.negated()方法:

**例 1:**

```
// Java code to illustrate negated() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the duration negated using negated() method
        System.out.println(duration1.negated());
    }
}
```

**输出:**

```
PT-51H-4M

```

**例 2:**

```
// Java code to illustrate negated() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration
        Duration duration2
            = Duration.ofDays(5);

        // Get the duration negated
        // using negated() method
        System.out.println(duration2.negated());
    }
}
```

**输出:**

```
PT-120H

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html #否定–](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#negated--)