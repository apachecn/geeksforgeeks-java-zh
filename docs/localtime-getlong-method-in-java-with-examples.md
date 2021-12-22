# Java 中的 LocalTime getLong()方法，带示例

> 原文:[https://www . geesforgeks . org/local time-getlong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-getlong-method-in-java-with-examples/)

**本地时间类**的 **getLong()** 方法有助于从该本地时间中获取作为参数传递的指定字段的值作为长值。此方法这次查询字段的值，返回值将始终在字段值的有效范围内。当字段不受支持且方法无法返回长值时，将引发异常。

**语法:**

```java
public long getLong(TemporalField field)
```

**参数:**此方法接受单个参数**临时字段**，即要获取的字段。它不应为空。
**返回值:**该方法返回字段的**长值**。
**异常:**该方法抛出以下异常:

*   **日期时间异常:**如果无法获得该字段的值或该值超出了该字段的有效值范围。
*   **如果不支持该字段或值的范围超过了一个长整型，则不支持该字段。**
*   **算术异常:**如果出现数值溢出。

下面的程序说明了 getLong()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// LocalTime.getLong() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {
        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // get Mili of Second value from LocalTime
        // using get method
        long secondvalue
            = time.getLong(ChronoField.MILLI_OF_SECOND);

        // prlong result
        System.out.println("MilliSecond Field: "
                           + secondvalue);
    }
}
```

**Output**

```java
MilliSecond Field: 630
```

**程序 2:** 获取不支持的临时类型异常

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// LocalTime.getLong() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {
        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // try to find era using ChronoField
        try {

            long secondvalue
                = time.getLong(ChronoField.YEAR);
        }
        catch (Exception e) {

            // prlong exception
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:** 

```java
Exception: java.time.temporal.UnsupportedTemporalTypeException: Unsupported field: Year
```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # getLong(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#getLong(java.time.temporal.TemporalField))