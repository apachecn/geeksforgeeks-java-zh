# Java 中从(TemporalUnit)方法开始的持续时间，示例

> 原文:[https://www . geeksforgeeks . org/duration-from emporalunit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-fromtemporalunit-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的 **from(TemporalUnit)** 方法用于从作为 TemporalUnit 中第一个参数传递的金额中获取持续时间。时间单位可以是天、小时等。

**语法:**

```java
public static Duration from(TemporalUnit amount)

```

**参数:**该方法接受一个参数**量**，该量是要从中找到持续时间的量，作为时间单位传递。

**返回值:**该方法返回一个表示指定金额时间的**持续时间**。

**异常:**此方法抛出以下单位:

*   **Arithmetic exception** : If there is a numerical overflow.
*   **Abnormal date and time** : If it can't be converted into duration.

以下示例说明了 Duration.from()方法:

**例 1:**

```java
// Java code to illustrate from() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Get the amount
        Duration duration = Duration.ofDays(5);

        // Duration using from() method
        Duration duration1 = Duration.from(duration);

        System.out.println(duration1.getSeconds());
    }
}
```

**输出:**

```java
432000

```

**例 2:**

```java
// Java code to illustrate from() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Get the amount
        Duration duration = Duration.ofHours(5);

        // Duration using from() method
        Duration duration1 = Duration.from(duration);

        System.out.println(duration1.getSeconds());
    }
}
```

**输出:**

```java
18000

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#from-java.time.temporal.TemporalAmount-)