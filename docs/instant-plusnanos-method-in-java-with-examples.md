# Java 中的 Instant plusNanos()方法，示例

> 原文:[https://www . geesforgeks . org/instant-plusnanos-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-plusnanos-method-in-java-with-examples/)

**Instant 类**的 **plusNanos()** 方法将作为参数传递的纳秒值添加到该瞬间，并将结果作为即时对象返回。这个返回的即时消息是不可变的。

**语法:**

```java
public Instant plusNanos(long nanosToAdd)
```

**参数:**该方法接受一个参数**nanostoad**，需要加上纳秒。

**返回:**此方法返回**瞬间**，不为空。

**异常:**如果结果超过最大或最小瞬间，该方法抛出以下异常:

*   **日期时间异常:**。
*   **Arithmetic exception:** If there is a numerical overflow.

下面的程序说明了 plusNanos()方法:

**程序 1:**

```java
// Java program to demonstrate
// Instant.plusNanos() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-10-28T19:34:50.63Z");

        // addition of 840000000 nanoseconds
        // means .84 seconds to this instant
        Instant returnedValue
            = instant.plusNanos(840000000);

        // print result
        System.out.println("Returned Instant: "
                           + returnedValue);
    }
}
```

**输出:**

```java
Returned Instant: 2018-10-28T19:34:51.470Z

```

**程序二:**

```java
// Java program to demonstrate
// Instant.plusNanos() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant = Instant.now();

        // current Instant
        System.out.println("Current instant: "
                           + instant);

        // addition of 430000000 nanoseconds
        // means .43 seconds to this instant
        Instant returnedValue
            = instant.plusNanos(430000000);

        // print result
        System.out.println("Returned Instant: "
                           + returnedValue);
    }
}
```

**输出:**

```java
Current instant: 2018-11-28T05:32:40.818Z
Returned Instant: 2018-11-28T05:32:41.248Z

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # plusNanos(长)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#plusNanos(long))