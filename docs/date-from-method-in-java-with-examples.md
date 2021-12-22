# Java 中的 Date from()方法，示例

> 原文:[https://www . geesforgeks . org/date-from-method-in-Java-with-examples/](https://www.geeksforgeeks.org/date-from-method-in-java-with-examples/)

[Java 日期类](https://www.geeksforgeeks.org/date-class-java-examples/)的 from(*inst inst*)方法返回一个从 Instant 对象获得的日期实例。

**语法:**

```
public static Date from(Instant inst)
```

**参数:**该方法取一个需要转换的即时型参数 *inst* 。

**返回值:**该方法返回一个日期，该日期表示时间线上与过去瞬间相同的点。

**异常:**

*   NullPointerException:当该瞬间为空时抛出。
*   IllegalArgumentException:当瞬间太大而无法表示为日期时抛出。

下面的程序说明了 from()方法在 Java 中的使用:
**示例 1:**

```
// Java code to demonstrate
// from() method of Date class

import java.time.Instant;
import java.util.Date;

public class JavaDateDemo {
    public static void main(String args[])
    {
        // Creating Date Object
        Date dateOne = new Date();

        // Creating Instant object
        Instant inst = Instant.now();

        // Displaying the instant
        System.out.println(
            "Present: "
            + dateOne.from(inst));
    }
}
```

**Output:**

```
Present: Tue Mar 26 06:45:40 UTC 2019

```

**例 2:**

```
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
            "Date: " + dateOne.from(inst));
    }
}
```

**Output:**

```
Date: Wed Jan 30 06:45:43 UTC 2019

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/date . html # from-Java . time . instant-](https://docs.oracle.com/javase/8/docs/api/java/util/Date.html#from-java.time.Instant-)