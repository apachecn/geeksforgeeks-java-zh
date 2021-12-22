# Java 中的 LocalDate minusWeeks()方法，示例

> 原文:[https://www . geesforgeks . org/local date-mins weeks-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-minusweeks-method-in-java-with-examples/)

Java 中一个 **LocalDate** 类的**mins weeks()**方法用于从这个 LocalDate 中减去指定的周数，并返回 LocalDate 的副本。例如，2018-12-24 减去一周将导致 2018-12-17。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public LocalDate minusWeeks(long weeksToSubtract)

```

**参数:**该方法接受单个参数**周减去**，代表要减去的周，可以是负数。

**返回值:**该方法返回基于该日期减去周数的**本地日期**，不为空。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

以下程序说明了负周()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalDate.minusWeeks() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate date
            = LocalDate.parse("2018-12-26");

        // print instance
        System.out.println("LocalDate before"
                           + " subtracting weeks: " + date);

        // subtract 2 weeks
        LocalDate returnvalue
            = date.minusWeeks(2);

        // print result
        System.out.println("LocalDate after "
                           + " subtracting weeks: " + returnvalue);
    }
}
```

**Output:**

```java
LocalDate before subtracting weeks: 2018-12-26
LocalDate after  subtracting weeks: 2018-12-12

```

**程序 2:**

```java
// Java program to demonstrate
// LocalDate.minusWeeks() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate date
            = LocalDate.parse("2018-12-24");

        // print instance
        System.out.println("LocalDate before"
                           + " subtracting weeks: " + date);

        // subtract -13 weeks
        LocalDate returnvalue
            = date.minusWeeks(-13);

        // print result
        System.out.println("LocalDate after "
                           + " subtracting weeks: " + returnvalue);
    }
}
```

**Output:**

```java
LocalDate before subtracting weeks: 2018-12-24
LocalDate after  subtracting weeks: 2019-03-25

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # mins weeks(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#minusWeeks(long))