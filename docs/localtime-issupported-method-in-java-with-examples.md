# Java 中的 LocalTime isSupported()方法，示例

> 原文:[https://www . geesforgeks . org/local time-issupported-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-issupported-method-in-java-with-examples/)

在 LocalTime 类中，根据传递给它的参数，有两种类型的 isSupported()方法。

### 问题支持(临时字段)

**一个 **LocalTime** 类的 isSupported()** 方法用来检查指定的字段是否被 LocalTime 类支持意味着使用这个方法我们可以检查这个 LocalTime 是否可以查询到指定的字段。
时空领域支持的领域有:

*   第二纳米
*   微秒
*   毫欧秒
*   即时 _ 秒
*   第二分钟
*   纳米日
*   微观 _OF_DAY
*   百万分之日
*   第二天
*   分钟/小时
*   每天分钟
*   AMPM 时间
*   AMPM 时间
*   一天中的小时
*   一天中的钟点
*   当日 AMPM

所有其他时间域实例都将返回 false。
**语法:**

```java
public boolean isSupported(TemporalField field)
```

**参数:**此方法接受一个单参数**字段**，即要检查的字段。
**返回值:**如果此 LocalTime 支持该字段，则该方法返回**布尔值【true，否则返回 false。
以下程序说明了 isSupported()方法:
**程序 1:**** 

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// LocalTime.isSupported() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime lt
            = LocalTime.parse("19:34:50.63");

        // check Milli of Second is supported in LocalTime
        boolean value
            = lt.isSupported(ChronoField.MILLI_OF_SECOND);

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

**一个 **LocalTime** 类的 isSupported()** 方法用来检查指定的单位是否被 LocalTime 类支持意味着使用这个方法我们可以检查这个 LocalTime 是否可以查询到指定的单位。
计时单位支持的字段有:

*   纳诺斯
*   MICROS
*   莫利斯
*   秒
*   分钟
*   小时
*   半天

所有其他计时单位实例将返回 false。
**语法:**

```java
public boolean isSupported(TemporalUnit unit)
```

**参数:**该方法只接受一个参数**单位**，即要检查的单位。
**返回值:**如果此 LocalTime 支持该字段，则该方法返回**布尔值【true，否则返回 false。
以下程序说明了 isSupported()方法:
**程序 1:**** 

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// LocalTime.isSupported() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime lt
            = LocalTime.parse("19:34:50.63");

        // check MILLIS ChronoUnit supported in LocalTime
        boolean value
            = lt.isSupported(ChronoUnit.MILLIS);

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

**参考:**

*   [https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # isSupported(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#isSupported(java.time.temporal.TemporalField))
*   [https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # isSupported(Java . time . temporal unit)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#isSupported(java.time.temporal.TemporalUnit))