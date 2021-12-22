# Java 中的 Date toInstant()方法，带示例

> 原文:[https://www . geesforgeks . org/date-to instant-method-in-Java-with-examples/](https://www.geeksforgeeks.org/date-toinstant-method-in-java-with-examples/)

Java 中[日期类](https://www.geeksforgeeks.org/date-class-java-examples/)的 **toInstant()** 方法用于将日期对象转换为即时对象。转换过程中会创建一个“瞬间”，用于表示时间线上与此日期相同的点。

**语法:**

```java
public Instant toInstant()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个**瞬间**，代表时间线上与该日期相同的点。

下面的程序说明了如何在 Java 中使用 toInstant()方法:
**示例 1:**

```java
// Java code to demonstrate
// toInstant() method of Date class

import java.util.Date;
import java.util.Calendar;
import java.time.Instant;

public class GfG {
    public static void main(String args[])
    {
        // Creating a Calendar object
        Calendar c1 = Calendar.getInstance();

        // Set Month
        // MONTH starts with 0 i.e. ( 0 - Jan)
        c1.set(Calendar.MONTH, 00);

        // Set Date
        c1.set(Calendar.DATE, 30);

        // Set Year
        c1.set(Calendar.YEAR, 2019);

        // Creating a date object
        // with specified time.
        Date dateOne = c1.getTime();

        Instant inst = dateOne.toInstant();

        System.out.println(
            "Original Date: "
            + dateOne.toString());
        System.out.println(
            "Instant: " + inst);
    }
}
```

**Output:**

```java
Original Date: Wed Jan 30 06:01:46 UTC 2019
Instant: 2019-01-30T06:01:46.730Z

```

**例 2:**

```java
// Java code to demonstrate
// clone() method of Date class

import java.util.Date;
import java.util.Calendar;
import java.time.Instant;

public class GfG {
    public static void main(String args[])
    {
        // Creating a Calendar object
        Calendar c1 = Calendar.getInstance();

        // Set Month
        // MONTH starts with 0 i.e. ( 0 - Jan)
        c1.set(Calendar.MONTH, 06);

        // Set Date
        c1.set(Calendar.DATE, 12);

        // Set Year
        c1.set(Calendar.YEAR, 1996);

        // Creating a date object
        // with specified time.
        Date dateOne = c1.getTime();

        Instant inst = dateOne.toInstant();

        System.out.println(
            "Original Date: "
            + dateOne.toString());
        System.out.println(
            "Instant: " + inst);
    }
}
```

**Output:**

```java
Original Date: Fri Jul 12 06:01:49 UTC 1996
Instant: 1996-07-12T06:01:49.766Z

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/date . html # to instant–](https://docs.oracle.com/javase/8/docs/api/java/util/Date.html#toInstant--)