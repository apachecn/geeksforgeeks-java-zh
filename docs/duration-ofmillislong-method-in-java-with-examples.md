# Java 中的 milis(long)方法持续时间举例

> 原文:[https://www . geesforgeks . org/duration-of milislong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-ofmillislong-method-in-java-with-examples/)

**java.time 包**中**时长类**的**of milis(long)**方法用于获取 1 毫秒格式的时长。

**语法:**

```java
public static Duration ofMillis(long milliSeconds)

```

**参数:**该方法接受一个参数**毫秒**，即毫秒数。它可以是积极的，也可以是消极的。

**返回值:**该方法返回一个**持续时间**，以 1 毫秒的格式表示时间。

**异常:**如果输入毫秒数超过持续时间的容量，该方法抛出**算法异常**。

以下示例说明了 Duration.ofMillis()方法:

**例 1:**

```java
// Java code to illustrate ofMillis() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Millis
        long noOfMillis = 50000;

        // Duration using ofMillis() method
        Duration duration
            = Duration.ofMillis(noOfMillis);

        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```java
50

```

**例 2:**

```java
// Java code to illustrate ofMillis() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Millis
        long noOfMillis = -445000;

        // Duration using ofMillis() method
        Duration duration
            = Duration.ofMillis(noOfMillis);

        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```java
-445

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # of millis-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#ofMillis-long-)