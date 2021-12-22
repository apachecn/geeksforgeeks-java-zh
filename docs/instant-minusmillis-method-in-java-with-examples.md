# Java 中的即时毫秒()方法，示例

> 原文:[https://www . geesforgeks . org/instant-mins millis-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-minusmillis-method-in-java-with-examples/)

**即时类**的**亚毫秒()**方法从这个瞬间减去以毫秒为单位的指定持续时间，并将结果作为即时对象返回。这个返回的即时消息是不可变的。

**语法:**

```java
public Instant minusMillis(long millisToSubtract)
```

**参数:**该方法接受一个参数**毫秒减去**，即毫秒减去。

**返回:**此方法在减去毫秒后返回**瞬间**。

**异常:**此方法抛出以下异常:

*   **datetimeexception** : If the result exceeds the maximum or minimum moment.
*   **Arithmetic exception** : If there is a numerical overflow.

以下程序说明了负毫秒()方法:

**程序 1:**

```java
// Java program to demonstrate
// Instant.minusMillis() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // subtract 64000000 MILLI_OF_SECOND
        // means 64000 seconds from this instant
        Instant returnedValue
            = instant.minusMillis(64000000);

        // print result
        System.out.println("Returned Instant: "
                           + returnedValue);
    }
}
```

**输出:**

```java
Returned Instant: 2018-12-30T01:48:10.630Z

```

**程序二:**

```java
// Java program to demonstrate
// Instant.minusMillis() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant = Instant.now();

        // current Instant
        System.out.println("current instant: "
                           + instant);

        // subtract 36000000 MILLI_OF_SECOND
        // means 36000 seconds from this instant
        Instant returnedValue
            = instant.minusMillis(36000000);

        // print result
        System.out.println("Returned Instant: "
                           + returnedValue);
    }
}
```

**输出:**

```java
current instant: 2018-11-27T05:13:12.132Z
Returned Instant: 2018-11-26T19:13:12.132Z

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # mins millis(长)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#minusMillis(long))