# Java 中的 LocalDate plusDays()方法，带示例

> 原文:[https://www . geesforgeks . org/local date-plus days-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-plusdays-method-in-java-with-examples/)

Java 中一个 **LocalDate** 类的 **plusDays()** 方法用于在这个 LocalDate 中添加指定的天数，并返回 LocalDate 的副本。例如，2018-12-31 加上一天将导致 2019-01-01。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public LocalDate plusDays(long daysToAdd)

```

**参数:**该方法接受单个参数*日添加*，表示要添加的天数，可以是负数。

**返回值:**此方法返回一个基于此日期加上天数的*本地日期*，不为空。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

下面的程序说明了 plusDays()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalDate.plusDays() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate date
            = LocalDate.parse("2018-11-13");

        // print instance
        System.out.println("LocalDate before"
                           + " adding days: " + date);

        // add 5 days
        LocalDate returnvalue
            = date.plusDays(5);

        // print result
        System.out.println("LocalDate after "
                           + " adding days: " + returnvalue);
    }
}
```

**Output:**

```java
LocalDate before adding days: 2018-11-13
LocalDate after  adding days: 2018-11-18

```

**程序 2:**

```java
// Java program to demonstrate
// LocalDate.plusDays() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate date
            = LocalDate.parse("2018-12-24");

        // print instance
        System.out.println("LocalDate before"
                           + " adding days: " + date);

        // add 15 days
        LocalDate returnvalue
            = date.plusDays(15);

        // print result
        System.out.println("LocalDate after "
                           + " adding days: " + returnvalue);
    }
}
```

**Output:**

```java
LocalDate before adding days: 2018-12-24
LocalDate after  adding days: 2019-01-08

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # plusDays(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#plusDays(long))