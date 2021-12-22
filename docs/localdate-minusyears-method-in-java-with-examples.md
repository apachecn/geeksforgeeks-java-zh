# Java 中的 LocalDate minusYears()方法，示例

> 原文:[https://www . geesforgeks . org/local date-mins years-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-minusyears-method-in-java-with-examples/)

一个 **LocalDate** 类的 **minusYears()** 方法用于从这个 LocalDate 中减去指定的年数，并返回 LocalDate 的副本。

此方法在以下步骤中减去年份字段:

*   首先，它从本地日期的年份字段中减去年份。
*   检查减去年份后的日期是否有效。
*   如果日期无效，则方法会将月中的某一天调整为最后一个有效日期。

例如，2016-02-29(闰年)减去一年得出日期 2015-02-29，但这是一个无效的结果，因此返回该月的最后一个有效日期 2015-02-28。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public LocalDate minusYears(long yearsToSubtract)

```

**参数:**该方法接受单个参数 **yearsToSubtract** ，代表要减去的年份，可以是负数。

**返回值:**该方法返回一个基于该日期减去年份的**本地日期**，不为空。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

以下程序说明了负年()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalDate.minusYears() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate date
            = LocalDate.parse("2020-10-22");

        // print instance
        System.out.println("LocalDate before"
                           + " subtracting years:" + date);

        // subtract 30 years
        LocalDate returnvalue
            = date.minusYears(30);

        // print result
        System.out.println("LocalDate after "
                           + " subtracting years:" + returnvalue);
    }
}
```

**Output:**

```java
LocalDate before subtracting years:2020-10-22
LocalDate after  subtracting years:1990-10-22

```

**程序 2:**

```java
// Java program to demonstrate
// LocalDate.minusYears() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate date
            = LocalDate.parse("2020-02-29");

        // print instance
        System.out.println("LocalDate before"
                           + " subtracting years: " + date);

        // subtract -21 years
        LocalDate returnvalue
            = date.minusYears(-21);

        // print result
        System.out.println("LocalDate after "
                           + " subtracting years: " + returnvalue);
    }
}
```

**Output:**

```java
LocalDate before subtracting years: 2020-02-29
LocalDate after  subtracting years: 2041-02-28

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # mins years(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#minusYears(long))