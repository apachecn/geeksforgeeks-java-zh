# Java 中的 LocalDate plusMonths()方法，示例

> 原文:[https://www . geesforgeks . org/local date-plusmonths-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-plusmonths-method-in-java-with-examples/)

Java 中 **LocalDate** 类的 **plusMonths()** 方法用于在这个 LocalDate 中添加指定的月数，并返回 LocalDate 的副本。

此方法通过以下步骤添加月份字段:

*   将月份添加到年度月份字段中。
*   检查添加月份后的日期是否有效。
*   如果日期无效，则方法将月日调整为最后一个有效日期。

例如，2018-08-31 加上一个月给出了日期 2018-09-31，但这是无效的结果，因此返回该月的最后一个有效日期 2018-09-30。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public LocalDate plusMonths(long monthsToAdd)

```

**参数:**此方法接受单个参数**月至日**，代表要添加的月份，可以是负数。

**返回值:**该方法返回一个基于该日期的**本地日期**，加上月份，不为空。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

下面的程序说明了 plusMonths()方法:
**程序 1:**

```
// Java program to demonstrate
// LocalDate.plusMonths() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate date
            = LocalDate.parse("2018-11-13");

        // print instance
        System.out.println("LocalDate before"
                           + " adding months: " + date);

        // add 5 months
        LocalDate returnvalue
            = date.plusMonths(5);

        // print result
        System.out.println("LocalDate after "
                           + " adding months: " + returnvalue);
    }
}
```

**Output:**

```
LocalDate before adding months: 2018-11-13
LocalDate after  adding months: 2019-04-13

```

**程序 2:**

```
// Java program to demonstrate
// LocalDate.plusMonths() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate date
            = LocalDate.parse("2018-12-31");

        // print instance
        System.out.println("LocalDate before"
                           + " adding months: " + date);

        // add 9 months
        LocalDate returnvalue
            = date.plusMonths(9);

        // print result
        System.out.println("LocalDate after "
                           + " adding months: " + returnvalue);
    }
}
```

**Output:**

```
LocalDate before adding months: 2018-12-31
LocalDate after  adding months: 2019-09-30

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # plusMonths(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#plusMonths(long))