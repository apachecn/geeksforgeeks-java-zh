# Java 中的 LocalDate minusDays()方法，示例

> 原文:[https://www . geesforgeks . org/local date-mind days-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-minusdays-method-in-java-with-examples/)

Java 中 **LocalDate** 类的 **minusDays()** 方法，用于从这个 LocalDate 中减去指定的天数，返回 LocalDate 的一个副本。例如，2019-01-01 减去一天将导致 2018-12-31。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public LocalDate minusDays(long daysToSubtract)

```

**参数:**该方法接受单个参数**日减去**，表示要减去的天数，可以是负数。

**返回值:**该方法返回基于该日期减去天数的**本地日期**，不为空。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

以下程序说明了天数()方法:
**程序 1:**

```java
// Java program to demonstrate
// LocalDate.minusDays() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate date
            = LocalDate.parse("2018-11-13");

        // print instance
        System.out.println("LocalDate before"
                           + " subtracting days: " + date);

        // subtract 17 days
        LocalDate returnvalue
            = date.minusDays(17);

        // print result
        System.out.println("LocalDate after "
                           + " subtracting days: " + returnvalue);
    }
}
```

**Output:**

```java
LocalDate before subtracting days: 2018-11-13
LocalDate after  subtracting days: 2018-10-27

```

**程序 2:**

```java
// Java program to demonstrate
// LocalDate.minusDays() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate date
            = LocalDate.parse("2018-12-24");

        // print instance
        System.out.println("LocalDate before"
                           + " subtracting days: " + date);

        // subtract -15 days
        LocalDate returnvalue
            = date.minusDays(-15);

        // print result
        System.out.println("LocalDate after "
                           + " subtracting days: " + returnvalue);
    }
}
```

**Output:**

```java
LocalDate before subtracting days: 2018-12-24
LocalDate after  subtracting days: 2019-01-08

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # mindsdays(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#minusDays(long))