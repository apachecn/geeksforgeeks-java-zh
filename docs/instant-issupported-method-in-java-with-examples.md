# Java 中的即时发布支持()方法，示例

> 原文:[https://www . geesforgeks . org/instant-issupported-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-issupported-method-in-java-with-examples/)

在 Instant 类中，根据传递给它的参数，有两种类型的 isSupported()方法。

### 问题支持(临时字段)

**isSupported()** 一个 **Instant** 类的方法用来检查指定的字段是否被 Instant 类支持就是说使用这个方法我们可以检查这个 Instant 是否可以查询到指定的字段。

计时场支持的字段有:

*   第二纳米
*   微秒
*   毫欧秒
*   即时 _ 秒

所有其他时间域实例都将返回 false。

**语法:**

```java
public boolean isSupported(TemporalField field)
```

**参数:**此方法接受一个单参数**字段**，即要检查的字段。
**返回值:**此方法返回**布尔值**。如果该字段在此时刻受支持，则返回 true，否则返回 false。

下面的程序说明了 isSupported()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Instant.isSupported() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // check Milli of Second value from instant
        boolean value
            = instant.isSupported(
                ChronoField.MILLI_OF_SECOND);

        // print result
        System.out.println("MilliSecond Field is supported: "
                           + value);
    }
}
```

**Output**

```java
MilliSecond Field is supported: true
```

### 发行支持(临时单位)

**isSupported()** 一个 **Instant** 类的方法用来检查 Instant 类是否支持指定的单位意味着使用这个方法我们可以检查这个 Instant 是否可以查询到指定的单位。

计时单位支持的字段有:

*   纳诺斯
*   MICROS
*   莫利斯
*   秒
*   分钟
*   小时
*   半天
*   天

所有其他计时单位实例将返回 false。

**语法:**

```java
public boolean isSupported(TemporalUnit unit)
```

**参数:**该方法只接受一个参数**单位**，即要检查的单位。
**返回值:**如果该字段在该时刻被支持，则该方法返回**布尔值【true，否则返回 false。**

下面的程序说明了 isSupported()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Instant.isSupported() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // check MILLIS ChronoUnit supported in instant
        boolean value
            = instant.isSupported(ChronoUnit.MILLIS);

        // print result
        System.out.println("ChronoUnit MILLIS is  supported: "
                           + value);
    }
}
```

**Output:** 

```java
ChronoUnit MILLIS is  supported: true
```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # isSupported(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#isSupported(java.time.temporal.TemporalField))[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # isSupported(Java . time . temporal nit)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#isSupported(java.time.temporal.TemporalUnit))