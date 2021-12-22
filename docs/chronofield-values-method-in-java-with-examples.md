# Java 中的计时字段值()方法，示例

> 原文:[https://www . geesforgeks . org/chronofield-values-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronofield-values-method-in-java-with-examples/)

**时间域枚举**的**值()**方法用于包含该枚举类型常数的数组，按顺序声明。

**语法:**

```java
public static ChronoField[] values()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回一个包含这个枚举类型的常量的数组，按照它们被声明的顺序。

下面的程序说明了时间域值()方法:
**程序 1:**

```java
// Java program to demonstrate
// ChronoField.values() method

import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // get chronoField
        ChronoField chronoField
            = ChronoField.valueOf("HOUR_OF_DAY");

        // apply values()
        ChronoField[] array
            = chronoField.values();

        // print
        for (int i = 0; i < array.length; i++)
            System.out.println(array[i]);
    }
}
```

**Output:**

```java
NanoOfSecond
NanoOfDay
MicroOfSecond
MicroOfDay
MilliOfSecond
MilliOfDay
SecondOfMinute
SecondOfDay
MinuteOfHour
MinuteOfDay
HourOfAmPm
ClockHourOfAmPm
HourOfDay
ClockHourOfDay
AmPmOfDay
DayOfWeek
AlignedDayOfWeekInMonth
AlignedDayOfWeekInYear
DayOfMonth
DayOfYear
EpochDay
AlignedWeekOfMonth
AlignedWeekOfYear
MonthOfYear
ProlepticMonth
YearOfEra
Year
Era
InstantSeconds
OffsetSeconds

```

**程序 2:**

```java
// Java program to demonstrate
// ChronoField.values() method

import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // get chronoField
        ChronoField chronoField
            = ChronoField.valueOf("HOUR_OF_DAY");

        // apply values()
        ChronoField[] array
            = chronoField.values();

        // print
        System.out.println("ChronoField length:"
                           + array.length);
    }
}
```

**Output:**

```java
ChronoField length:30

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/chronofield . html # values()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoField.html#values())