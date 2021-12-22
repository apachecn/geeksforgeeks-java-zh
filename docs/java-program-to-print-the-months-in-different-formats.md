# Java 程序打印不同格式的月份

> 原文:[https://www . geesforgeks . org/Java-程序-打印不同格式的月份/](https://www.geeksforgeeks.org/java-program-to-print-the-months-in-different-formats/)

对于不同格式的打印月份，我们将使用两类 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包。这是第一个[日历类](https://www.geeksforgeeks.org/calendar-class-in-java-with-examples/)，另一个是[格式化程序类。](https://docs.oracle.com/javase/7/docs/api/java/util/Formatter.html)从 Calendar 类使用 [getInstance()方法](https://www.geeksforgeeks.org/calendar-getinstance-method-in-java-with-examples/)根据当前时区获取日历的实例(时间和日期信息)。

**例:**

```java
Input : 18-11-2020
Output: December Dec 12
Explaination: Here, month starts from 0.

Input : 18-5-2019
Output: June Jun 06
```

**语法:**

```java
public static Calendar getInstance()
```

**返回值:**该方法返回日历。

**格式化程序类:**

java 中的 Formatter 类主要用来显示数字、字符串、时间、日期任何你喜欢的格式。以下是我们程序中用于格式化日期的转换字符。

1.  %tB- The whole month is named as "January" and "March".
2.  % TB- abbreviated month names, such as "January" and "February".
3.  % TM- The month format is two digits.

下面实现中使用的格式:

```java
"November" "NOV" "11"
```

实现:

## Java

```java
// Java Program to Print the Months in Different Formats
import java.util.Calendar;
import java.util.Formatter;

public class MonthFormates {
    public static void main(String args[])
    {

        // create objects of date formatter class.
        Formatter fmt1 = new Formatter();

        // create object of calendar class.
        // cal object contains current date of system
        Calendar cal = Calendar.getInstance();

        // setting a new date and Here 5 means
        // June because Months starts from 0
        cal.set(2019, 5, 18);

        // print month in different ways.
        fmt1.format("%tB %tb %tm", cal, cal, cal);
        System.out.println("Output: " + fmt1);
    }
}
```

**输出**

```java
Output: June Jun 06

```