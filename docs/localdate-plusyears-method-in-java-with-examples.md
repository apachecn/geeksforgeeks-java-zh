# Java 中的 LocalDate plusYears()方法，带示例

> 原文:[https://www . geesforgeks . org/local date-plusyears-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-plusyears-method-in-java-with-examples/)

Java 中 **LocalDate** 类的 **plusYears()** 方法用于在这个 LocalDate 中添加指定的年数，并返回 LocalDate 的副本。

此方法通过以下步骤添加年份字段:

*   将年份添加到年份字段。
*   检查添加年份后的日期是否有效。
*   如果日期无效，则方法将月日调整为最后一个有效日期。

例如，2016-02-29(闰年)加上一年给出了日期 2017-02-29，但这是无效的结果，因此返回该月的最后一个有效日期 2017-02-28。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public LocalDate plusYears(long yearsToAdd)

```

**参数:**该方法接受单个参数**年到日**，代表要相加的年，可以是负数。

**返回值:**此方法返回一个基于此日期加上年份的**本地日期**，不为空。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

下面的程序说明了 plusYears()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalDate.plusYears() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate date
            = LocalDate.parse("2018-11-13");

        // print instance
        System.out.println("LocalDate before"
                           + " adding years: " + date);

        // add 3 years
        LocalDate returnvalue
            = date.plusYears(3);

        // print result
        System.out.println("LocalDate after "
                           + " adding years: " + returnvalue);
    }
}
```

**Output:**

```java
LocalDate before adding years: 2018-11-13
LocalDate after  adding years: 2021-11-13

```

**程序 2:**

```java
// Java program to demonstrate
// LocalDate.plusYears() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate date
            = LocalDate.parse("2016-02-29");

        // print instance
        System.out.println("LocalDate before"
                           + " adding years: " + date);

        // add 2 years
        LocalDate returnvalue
            = date.plusYears(2);

        // print result
        System.out.println("LocalDate after "
                           + " adding years: " + returnvalue);
    }
}
```

**Output:**

```java
LocalDate before adding years: 2016-02-29
LocalDate after  adding years: 2018-02-28

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # plusYears(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#plusYears(long))