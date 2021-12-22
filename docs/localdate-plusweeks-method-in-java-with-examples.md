# Java 中的 LocalDate plusWeeks()方法，带示例

> 原文:[https://www . geesforgeks . org/local date-plusweeks-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-plusweeks-method-in-java-with-examples/)

Java 中 **LocalDate** 类的 **plusWeeks()** 方法用于在这个 LocalDate 中添加指定的周数，并返回 LocalDate 的副本。例如，2018-12-24 加上一周将导致 2018-12-31。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public LocalDate plusWeeks(long weeksToAdd)

```

**参数:**该方法接受单个参数**周添加**，代表要添加的周，可以是负数。

**返回值:**此方法返回一个基于此日期加上周数的**本地日期**，不为空。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

下面的程序说明了 plusWeeks()方法:

**节目 1:**

```
// Java program to demonstrate
// LocalDate.plusWeeks() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate date
            = LocalDate.parse("2018-12-26");

        // print instance
        System.out.println("LocalDate before"
                           + " adding weeks: " + date);

        // add 5 weeks
        LocalDate returnvalue
            = date.plusWeeks(5);

        // print result
        System.out.println("LocalDate after "
                           + " adding weeks: " + returnvalue);
    }
}
```

**输出:**

```
LocalDate before adding weeks: 2018-12-26
LocalDate after  adding weeks: 2019-01-30

```