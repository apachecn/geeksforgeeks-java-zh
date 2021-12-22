# Java 中的 Instant ofEpochMilli()方法，带示例

> 原文:[https://www . geeksforgeeks . org/instant-ofepochmilli-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-ofepochmilli-method-in-java-with-examples/)

**Instant 类**的**of Pochmilli()**方法有助于使用从 1970-01-01T00:00:00Z 的时期作为参数传递的毫秒来获得 Instant。这个返回的毫秒用于通过转换获得不同的时间单位，如秒等。

**语法:**

```java
public static Instant 
    ofEpochMilli(long epochMilli)
```

**参数:**该方法接受一个参数 **epochMilli** 为 1970-01-01T00:00:00Z 的毫秒值。

**返回:**此方法返回**瞬间**作为从纪元开始的时间，单位为毫秒。

**异常:**如果结果超过最大或最小瞬间，该方法抛出**日期时间异常**。

下面的程序说明了 ofEpochMilli()方法:

**程序 1:**

```java
// Java program to demonstrate
// Instant.ofEpochMilli() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a long variable for milliseconds
        long milliseconds
            = 999999000;

        // get Instant using ofEpochMilli() method
        Instant instant
            = Instant.ofEpochMilli(milliseconds);

        // print result
        System.out.println("Instant: "
                           + instant);
    }
}
```

**输出:**

```java
Instant: 1970-01-12T13:46:39Z

```

**程序二:**

```java
// Java program to demonstrate
// Instant.ofEpochMilli() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // get Instant using ofEpochMilli() method
        // passed epoch millisecond is 73264271044L
        Instant instant
            = Instant.ofEpochMilli(73264271044L);

        // print result
        System.out.println("Instant: "
                           + instant);
    }
}
```

**输出:**

```java
Instant: 1972-04-27T23:11:11.044Z

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/Instant . html # ofEpochMilli(长)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#ofEpochMilli(long))