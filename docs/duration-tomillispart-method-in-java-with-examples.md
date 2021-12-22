# Java 中的 Duration toMillisPart()方法，示例

> 原文:[https://www . geesforgeks . org/duration-tomallispart-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-tomillispart-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的**TomilisPart()**方法用于通过将纳秒数除以 1，000，000 获得该持续时间的值，单位为毫秒。

**语法:**

```java
public long toMillisPart()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回一个**长值**，这个长值是这个持续时间内的毫秒数除以 1，000，000。

下面的例子说明了 Duration.toMillisPart()方法:

**例 1:**

```java
// Java code to illustrate toMillisPart() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration = Duration.parse("P2DT3H4M");

        System.out.println("Duration: "
                           + duration);

        // Get the number of milli-seconds
        // using toMillisPart() method
        System.out.println(duration.toMillisPart());
    }
}
```

**输出:**

```java
Duration: PT51H4M
0

```

**例 2:**

```java
// Java code to illustrate toMillisPart() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofMillis() method
        Duration duration = Duration.ofMillis(10);

        System.out.println("Duration: "
                           + duration);

        // Get the number of milli-seconds
        // using toMillisPart() method
        System.out.println(duration.toMillisPart());
    }
}
```

**输出:**

```java
Duration: PT0.01S
10

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # tomili part–](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toMillisPart--)