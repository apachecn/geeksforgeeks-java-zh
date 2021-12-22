# Java 中 nano(长)方法持续时间示例

> 原文:[https://www . geesforgeks . org/duration-with nanoslong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-withnanoslong-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的**with nano(long)**方法用于获取该持续时间的不可变副本，指定的 nano 秒数量作为参数传递。

**语法:**

```
public Duration withNanos(long amountOfNanos)

```

**参数:**该方法接受一个参数 **amountOfNanos** ，即纳米秒的量。

**返回值:**该方法返回作为参数传递的纳米秒的**持续时间**。

**异常:**如果纳秒无效，此方法抛出**日期时间异常**。

以下示例说明了 Duration.withNanos()方法:

**例 1:**

```
// Java code to illustrate withNanos() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Get the amount of nano-seconds
        int amountOfNanos = 30000;

        // Duration using parse() method
        Duration duration
            = Duration.parse("P2DT3H4M");

        // Get the duration in nano-seconds
        // using withNanos() method
        System.out.println(duration
                               .withNanos(amountOfNanos));
    }
}
```

**输出:**

```
PT51H4M0.00003S

```

**例 2:**

```
// Java code to illustrate withNanos() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Get the amount of nano-seconds
        int amountOfNanos = 100000;

        // Duration using ofHours() method
        Duration duration = Duration.ofHours(5);

        // Get the duration in nano-seconds
        // using withNanos() method
        System.out.println(duration
                               .withNanos(amountOfNanos));
    }
}
```

**输出:**

```
PT5H0.0001S

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # with nanos-int-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#withNanos-int-)