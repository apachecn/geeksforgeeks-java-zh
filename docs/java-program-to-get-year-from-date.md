# 从日期开始获取年份的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-get-year-from-date/](https://www.geeksforgeeks.org/java-program-to-get-year-from-date/)

Java 是最强大的编程语言，通过它我们可以执行许多任务，Java 是一种行业首选语言。所以它充满了大量的特征。在这里，我们将讨论 Java 最好的特性之一，即如何使用 Java 从日期中获取一年。

**方法:**

有很多种方法可以从日期中获取年份，下面列出了两种常用的方法。

1.  使用 get()方法本地日期类
2.  使用日历类的 get()方法
3.  使用字符串类的 split()方法

让我们在实现这些方法的同时详细讨论它们

**方法 1:** [使用 LocalDate 类的 get()方法](https://www.geeksforgeeks.org/localdate-get-method-in-java-with-examples/)

Java 方法中 LocalDate 类的 get()方法从该日期中获取指定字段的值作为 int。

**语法**:

```
public int get(TemporalField field)
```

**参数**:该方法接受一个参数*字段*，该字段是要获取的字段，不一定为空。

**返回值**:返回该字段的值。

**异常:**抛出三个异常，即:

*   DateTimeException:如果无法获取该字段的值或该值超出了该字段的有效值范围，则会引发此异常。
*   unsupportedtemporaltypexception:如果字段不受支持或值的范围超过了整数，则会引发此异常
*   算术异常:如果发生数值溢出，将引发此异常

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Get Year From Date
//  Using LocalDate class

// Importing Classes/Files
import java.time.LocalDate;
import java.time.Month;
import java.util.Date;

// Main class
class GFG {

    // Method 1
    // To get the year
    public static void getYear(String date)
    {
        // Getting an instance of LocalTime from date
        LocalDate currentDate = LocalDate.parse(date);

        // Getting year from date
        int year = currentDate.getYear();

        // Printing the year
        System.out.println("Year: " + year);
    }

    // Method 2
    // Main driver method
    public static void main(String args[])
    {
        // Specifying a date
        String date = "2021-05-21";

        // Function Call
        getYear(date);
    }
}
```

**输出:**

```
Year: 2021
```

**方法 2:** [使用日历类](https://www.geeksforgeeks.org/calendar-get-method-in-java-with-examples/)的 get()方法

Calendar 类的 get(int *field_value* )方法用于返回参数中给定日历字段的值。

**语法:**

```
public int get(int field)
```

**参数:**该方法取一个整型的参数 field_value，引用需要返回值的日历。

**返回值:**该方法返回传递字段的值。

> **注意:**在上面的程序中， ***get()方法*** *用于从指定日期开始获取年份。*

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Get Year From Date
// using Calendar class

// Importing Classes/Files
import java.util.*;

// main class
class GFG {

    // Main Driver Code
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar Cal
            = new GregorianCalendar(
                2021, 05, 21);

        // Getting the values of year from calendar
        // object
        int year = Cal.get(Calendar.YEAR);

        // Printing the year value
        System.out.println("Year: " + year);
    }
}
```

**输出:**

```
Year: 2021
```

**方法 3:** [使用*分裂()方法*的弦类](https://www.geeksforgeeks.org/split-string-java-examples/)

此方法确实会在给定正则表达式的匹配项周围断开给定的字符串。

**参数:**取两个参数，即:

*   正则表达式:一种定界正则表达式
*   限制:结果阈值

**返回类型:**通过拆分给定字符串计算的字符串数组。

**异常:** [模式同步异常](https://www.geeksforgeeks.org/regular-expressions-in-java/)–如果提供的正则表达式语法无效。

> 这里 String 类的 ***split()函数*** 用于按照给定的模式拆分指定的日期字符串，它返回一个字符串数组。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Get Year From Date
// Using String.split() method

// Main class
class GFG {

    // Method 1
    // To get year from date
    public static void findYear(String date)
    {
        // Splitting the given date by '-'
        String dateParts[] = date.split("-");

        // Getting year from date
        String year = dateParts[2];

        // Printing the year
        System.out.println("Year: " + year);
    }

    // Method 2
    // Main Driver Code
    public static void
    main(String args[])
    {
        // Given date
        String date = "21-05-2021";

        // Function calling
        findYear(date);
    }
}
```

**输出:**

```
Year: 2021
```