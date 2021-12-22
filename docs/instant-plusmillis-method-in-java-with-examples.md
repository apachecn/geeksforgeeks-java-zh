# Java 中的 Instant plusMillis()方法，示例

> 原文:[https://www . geesforgeks . org/instant-plusmillis-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-plusmillis-method-in-java-with-examples/)

**Instant 类**的 **plusMillis()** 方法将指定的持续时间(以毫秒为单位)添加到该瞬间，并将结果作为即时对象返回。这个返回的即时消息是不可变的。

**语法:**

```java
public Instant plusMillis(long millisToAdd)
```

**参数:**此方法接受一个参数**毫秒添加**，即毫秒添加。

**返回:**这个方法返回**瞬间**加上毫秒。

**异常:**如果结果超过最大或最小瞬间，该方法抛出以下异常:

*   **日期时间异常:**。
*   **Arithmetic exception:** If there is a numerical overflow.

下面的程序说明了 plusMillis()方法:

**节目 1:**

```java
// Java program to demonstrate
// Instant.plusMillis() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // addition of 8800000 MILLI_OF_SECOND
        // means 8800 seconds to this instant
        Instant returnedValue
            = instant.plusMillis(8800000);

        // print result
        System.out.println("Returned Instant: "
                           + returnedValue);
    }
}
```

**节目 2:**

```java
// Java program to demonstrate
// Instant.plusMillis() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant = Instant.now();

        // current Instant
        System.out.println("Current instant: "
                           + instant);

        // addition of 420000 MILLI_OF_SECOND
        // means 420 seconds to this instant
        Instant returnedValue
            = instant.plusMillis(420000);

        // print result
        System.out.println("Returned Instant: "
                           + returnedValue);
    }
}
```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # plusMillis(长)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#plusMillis(long))