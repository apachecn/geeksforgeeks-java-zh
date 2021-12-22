# Java 中 LocalDate、LocalTime、LocalDateTime 类常用的方法

> 原文:[https://www . geesforgeks . org/常用方法-in-local date-local time-and-local datetime-class-in-Java/](https://www.geeksforgeeks.org/commonly-used-methods-in-localdate-localtime-and-localdatetime-classes-in-java/)

Java 提供了与日期相关的三个最重要的类，即 **LocalDate** 、 **LocalTime、LocalDateTime** ，这使得在 Java 中处理日期变得非常容易，因为为了使用这些类，我们需要导入*'**Java . time '*****包，该包是日期、时间、瞬间和持续时间的主要 API。**

**插图:**

```
1\. java.time.* 
   // To include all classes

2\. java.time.LocalDate
   // for LocalDate

3\. java.time.LocalDateTime 
   // for LocalDateTime

4\. java.time.time 
   // for LocalTime
```

<figure class="table">

| 班级 | 描述 |
| --- | --- |
| **局部日期** | 本地日期类只能保存日期。例如，假设是 2021-02-28 |
| 局部时间 | 本地时间类只能保存时间。例如，假设是 19:32:25.457826 |
| **局部日期时间** | 本地日期时间类保存日期和时间。比如说是 2021-02-28T19:32:25.457826。在这种格式中，T 之前是日期，T 之后是时间。

 |

</figure>

**一般来说，导入包中所有不必要的文件被认为是不好的做法。因此，我们应该只导入需要的类。这些类中有各种方法可以根据类处理日期和时间。让我们讨论被称为*的 LocalDate 类中最常见的方法，现在是()*方法。**

****法:** [今()法](https://www.geeksforgeeks.org/localdate-now-method-in-java-with-examples/)**T5】****

**LocalDate 类的 now()方法，用于从默认时区的系统时钟中获取当前日期。此方法将根据系统时钟和默认时区返回本地日期，以获取当前日期。**

****语法:****

```
public static LocalDate now()
```

****返回值:**该方法使用系统时钟和默认时区返回当前日期。**

****例 1:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java Program to illustrate Commonly used methods in classes
// LocalDate, LocalTime and LocalDateTime Classes

// Importing input output classes
import java.io.*;
// Importing LocalDate, LocalTime, LocalDateTime classes
// from java.time package 
import java.time.LocalDate;
import java.time.LocalTime;
import java.time.LocalDateTime;

// Main class
class GFG {

    // Main driver method
    public static void main (String[] args) {

        // Creating instance of LocalDate class
        // using now() method
        LocalDate presentDate = LocalDate.now();

        // Print and display present date
        System.out.println(presentDate);

        // Creating instance of LocalDateTime class
        // using now() method
        LocalDateTime present = LocalDateTime.now();

        System.out.println(present);

        // Creating instance of LocalTime class
        // again using now() method
        LocalTime presentTime = LocalTime.now();

        // Print and display the current time 
        System.out.println(presentTime);
    }
}
```

****Output**

```
2021-02-28
2021-02-28T14:16:07.181034
14:16:07.181230
```** 

**我们将在实现部分的一段代码中讨论下表中显示的其余实用方法，这将在后面进一步讨论。所有已经讨论过的类，即 LocalDate、LocalDateTime、LocalTime 类都是不可变的，所有的修改方法都会返回新的对象，因此不会改变当前对象的值。**

**[LocalDate 类](https://www.geeksforgeeks.org/localdate-format-method-in-java/)提供的一些实用方法如下:**

<figure class="table"> **| way | describe |
| --- | --- |
| getDayOfMonth() | Returns a certain day of the current month. For example, say it is 28. |
| getDayOfWeek() | Return to working day. For example, say it is SUNDAY. |
| getdayofyeear() | Returns the last day of the year. Say 59. |
| getMonth（） | The name of the returned month. For example, say it is February. |
| getmonthvvalue() | Returns the value of the month. For example, say it is 2. |
| 岛耳() | Returns a Boolean value (true/false). For example, say it is false. |
| 年长度() | Returns the number of days in the current year. For example, suppose it is 365. |
| 月长() | Returns the number of days in the current year. For example, suppose ut is 28. |
| 加日（天数） | Add the number of days to the current date and return to the new date. |
| plusMonths(累计月数) | Add the number of months to the current date and return to the new date. |
| plusYears(奇数年数) | Add the number of years to the current date and return to the new date. |** </figure>

**类似的方法也可以用来减去日期。天数()，月数()，年数()。这些函数也可用于 LocalDateTime 类，增加了一些与时间相关的函数。比如 plusHours()，plusMinutes()，plusSeconds()，plusNanos()等等。**

****例 2:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java Program to illustrate Commonly used methods in
// classes LocalDate, LocalTime and LocalDateTime Classes

//  Importing input output classes
import java.io.*;
// Importing java.time package to import classes
// LocalDate, LocalTime and LocalDateTime
import java.time.LocalDate;
import java.time.LocalDateTime;
import java.time.LocalTime;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating object of LocalDate
        LocalDate presentDate = LocalDate.now();

        System.out.println(presentDate);

        // Creating object of LocalDateTime
        LocalDateTime present = LocalDateTime.now();

        System.out.println(present);

        // Creating object of LocalTime
        LocalTime presentTime = LocalTime.now();

        System.out.println(presentTime);

        // Implementing the LocalDate class methods
        // All methods of the table are shown below

        // Print the the day of the month
        System.out.println(presentDate.getDayOfMonth());

        // Print the weekday
        System.out.println(presentDate.getDayOfWeek());

        // Print the day w.r.t. the year
        System.out.println(presentDate.getDayOfYear());

        // Print the name of the month
        System.out.println(presentDate.getMonth());

        // Print the name of the month
        System.out.println(presentDate.getMonthValue());

        // Print the boolean value (true/false)
        System.out.println(presentDate.isLeapYear());

        // Print the number of days in that year
        System.out.println(presentDate.lengthOfYear());

        // Print the
        System.out.println(presentDate.lengthOfMonth());

        // Print the new date after adding the number of
        // days to the current date.
        System.out.println(presentDate.plusDays(50));

        // Print the new date after adding the number of
        // months to the current date.
        System.out.println(presentDate.plusMonths(50));

        // Print the new date after adding the number of
        // years to the current date.
        System.out.println(presentDate.plusYears(50));

        // Similarly for the rest of them.
        System.out.println(presentDate.minusDays(50));
        System.out.println(presentDate.minusMonths(50));
        System.out.println(presentDate.minusYears(50));

        // Implementing methods which are available in
        // LocalTime and LocalDateTime

        System.out.println(present.plusHours(100));
        System.out.println(present.plusMinutes(1000));
        System.out.println(present.plusSeconds(100000));
        System.out.println(present.plusNanos(1000000));
    }
}
```

****Output**

```
2021-02-28
2021-02-28T14:54:21.331923
14:54:21.332156
28
SUNDAY
59
FEBRUARY
2
false
365
28
2021-04-19
2025-04-28
2071-02-28
2021-01-09
2016-12-28
1971-02-28
2021-03-04T18:54:21.331923
2021-03-01T07:34:21.331923
2021-03-01T18:41:01.331923
2021-02-28T14:54:21.332923
```**