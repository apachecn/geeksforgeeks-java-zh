# Java 中的 Instant get()方法，示例

> 原文:[https://www . geesforgeks . org/instant-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-get-method-in-java-with-examples/)

**Instant 类**的 **get()** 方法有助于获取作为参数从该时刻作为整数值传递的指定字段的值。此方法立即查询字段的值，返回值将始终在字段值的有效范围内。当字段不受支持并且方法无法返回 int 值时，将引发异常。

**语法:**

```java
public int get(TemporalField field)
```

**参数:**该方法接受一个参数**字段**，即要获取的字段。
**返回:**该方法返回字段的 **int** 值。

**异常:**该方法抛出以下异常:

*   **日期时间异常**:如果无法获取字段的值或者该值超出了字段有效值的范围。
*   **unsupportedtemporaltypexception**:如果不支持该字段或者值的范围超过了一个整数。
*   **算术异常**:如果出现数值溢出。

**以下程序说明 get()方法:**

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Instant.get() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // get Milli of Second value from instant
        // using get method
        int secondvalue
            = instant.get(ChronoField.MILLI_OF_SECOND);

        // print result
        System.out.println("MilliSecond Field: "
                           + secondvalue);
    }
}
```

**Output**

```java
MilliSecond Field: 630
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Instant.get() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T01:34:50.93Z");

        // get Nano of Second value from instant
        // using get method
        int secondvalue
            = instant.get(ChronoField.NANO_OF_SECOND);

        // print result
        System.out.println("Nano of Second: "
                           + secondvalue);
    }
}
```

**Output:** 

```java
Nano of Second: 930000000
```

**程序 3:** 获取不支持的临时类型异常

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Instant.get() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T01:34:50.93Z");

        // try to find era using ChronoField
        try {

            int secondvalue
                = instant.get(ChronoField.ERA);
        }
        catch (Exception e) {

            // print exception
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:** 

```java
Exception:
 java.time.temporal.UnsupportedTemporalTypeException:
 Unsupported field: Era
```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # get(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#get(java.time.temporal.TemporalField))