# Java 中的 Instant now()方法，示例

> 原文:[https://www . geesforgeks . org/instant-now-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-now-method-in-java-with-examples/)

在 Instant 类中，根据传递给它的参数，有两种 now()方法。

### 现在()

**now()** 一个 **Instant** 类的方法，用于从系统 UTC 时钟获取当前的 Instant。此方法将根据系统协调世界时时钟返回即时消息。

**语法:**

```java
public static Instant now()

```

**参数:**该方法不接受参数。

**返回值:**该方法使用系统时钟返回当前时刻

下面的程序说明了 now()方法:
**程序 1:**

```java
// Java program to demonstrate
// Instant.now() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an Instant object
        Instant lt
            = Instant.now();

        // print result
        System.out.println("Instant : "
                           + lt);
    }
}
```

**Output:**

```java
Instant : 2019-01-21T05:47:26.853Z

```

### 现在(时钟)

**now(Clock clock)** 一个 **Instant** 类的方法，用于根据作为参数传递的指定时钟返回当前的 Instant。

**语法:**

```java
public static Instant now(Clock clock)

```

**参数:**该方法接受**时钟**作为参数，该参数是要使用的时钟。

**返回值:**此方法返回**当前瞬间**。

下面的程序说明了 now()方法:
**程序 1:**

```java
// Java program to demonstrate
// Instant.now() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a clock
        Clock cl = Clock.systemUTC();

        // create an Instant object using now(Clock)
        Instant lt
            = Instant.now(cl);

        // print result
        System.out.println("Instant : "
                           + lt);
    }
}
```

**Output:**

```java
Instant : 2019-01-21T05:47:29.886Z

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # now()](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#now())
[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # now(Java . time . clock)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#now(java.time.Clock))