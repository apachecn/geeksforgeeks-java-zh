# java 中的 java.time.MonthDay 类

> 原文:[https://www . geesforgeks . org/Java-time-monthday-class-in-Java/](https://www.geeksforgeeks.org/java-time-monthday-class-in-java/)

Java 是最流行的编程语言，也是应用最广泛的编程语言。Java 用于各种应用，如移动应用、桌面应用、网络应用。java.time.MonthDay 类表示一个月中的月和日的组合，并且是不可变的。 [java.time](https://www.geeksforgeeks.org/tag/java-time-package/) 是一个用来处理当前日期和时间 API 的包。下面以表格的形式讨论了这个类的所有方法。

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| 调整(时态) | 将指定的时态对象调整为有这个月日。 |
| at year(int year) | 将这个月日和一年结合起来，创建一个 LocalDate。 |
| 比较(月日其他) | 将本月日与另一个月日进行比较。 |
| 格式(datetime formatter) | 使用指定的格式化程序格式化这个月-日。 |
| getDayOfMonth() | 获取当月的日字段。 |
| getMonth() | 使用 Month 枚举获取年月字段。 |
| getmonthvvalue() | 获取从 1 到 12 的年月字段。 |
| hashCode() | 本月-日的一个 hash 码。 |
| is after(MonthDay other) | 检查此月-日是否在指定的月-日之后。 |
| 现在() | 从默认时区的系统时钟获取当前的月-日。 |
| 现在(时钟时钟) | 从指定的时钟获取当前的月-日。 |
| (int month，int dayOfMonth) | 获取 MonthDay 的一个实例。 |
| 查询(TemporalQuery < R >查询) | 使用指定查询查询本月-日。 |
| 范围(临时字段) | 获取指定字段的有效值范围。 |
| ToString() | 将本月日作为字符串输出，如–12-03。 |
| 带(月月) | 返回本月日的副本，其中年月日已更改。 |
| 带月日(int dayOfMonth) | 返回该月日的副本，其中更改了月日。 |
| with month(int month) | 返回该月的副本，其中更改了年月日。 |

</figure>

**实现:**现在我们来讨论一下这个类的几个方法

*   Import classes and packages java.time 。
*   Now use a method like MonthDay.of () or any other method and store an instance of MonthDay.
*   Displays the stored value in the variable.

**例 1**

## Java

```
// Java Program to illustrate MonthDay Class

// Importing Month and MonthDay classes
// from java.time package
import java.time.Month;
import java.time.MonthDay;

// Main Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of MonthDay class by
        // storing instance of MonthDay by
        // passing date and month as arguments

        // Custom inputs are passed as arguments
        MonthDay monthday = MonthDay.of(Month.MARCH, 14);

        // Print and display the value stored
        System.out.println(monthday);
    }
}
```

**输出**

```
--03-14
```

#### **Java**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate MonthDay Class

// importing MonthDay class from java.time
import java.time.MonthDay;

// Main Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Store an instance of MonthDay
        // from a text i.e --03-14
        MonthDay monthday = MonthDay.parse("--03-14");

        // Display the month using instance of class
        System.out.println(monthday.getMonth());
    }
}
```

**Output**

```
MARCH
```