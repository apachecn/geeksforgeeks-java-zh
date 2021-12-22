# 将日期转换为字符串的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-convert-date-to-string/](https://www.geeksforgeeks.org/java-program-to-convert-date-to-string/)

**日期类型对象**可以使用 Java 中可用的各种内置类在 Java 中转换为字符串。

给定一个日期，我们需要将日期转换为给定的字符串格式。

**示例:**

> ***输入:**日期=【2020-11-13】*
> T5**输出:** 2020-11-13
> 
> ***输入:**日期=【2020-12-14】*
> T5**输出:** 2020-12-14

**方法一:使用** [**日期格式**](https://www.geeksforgeeks.org/dateformat-format-method-in-java-with-examples/) **类**

*   [**日历类**](https://www.geeksforgeeks.org/calendar-class-in-java-with-examples/) 用于提供在任意时刻与一组日历字段进行交互的功能。日历类有一个内置的方法 **getInstance()** ，用来获取当前的日期和时间。它返回存储在日期类型变量中的日期。
*   [**【日期格式】**](https://www.geeksforgeeks.org/dateformat-format-method-in-java-with-examples/) **类**是一个内置的 Java 类，用于解析日期或时间值并设置其格式。我们可以使用**简单日期格式类**对象来指定日期的格式，该对象将日期格式作为参数，并返回日期格式说明符。

DateFormat 类有一个内置的方法 Format()，其语法如下:

```java
DateFormat.format(date_type_object) 
```

返回一个字符串变量，该变量对应于作为函数参数提供的日期类型对象。

**进场:**

1.  获取要转换的日期。
2.  创建一个实例[***【简单日期格式】***](https://www.geeksforgeeks.org/java-simpledateformat-set-1/) *类*来格式化日期对象的字符串表示。
3.  使用*日历对象*获取日期。
4.  使用 [***格式()***](https://www.geeksforgeeks.org/dateformat-format-method-in-java-with-examples/) *方法*将给定日期转换为字符串。
5.  打印结果。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to convert date to string
import java.text.DateFormat;
import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.Calendar;

public class DateToString {
    public static void main(String args[])
    {
        // used to fetch current date and time
        Date date = Calendar.getInstance().getTime();

        // specify the format yyyy-mm-dd to print current
        // date to as an argument
        DateFormat date_format = new SimpleDateFormat("yyyy-mm-dd");

        // print date in the specified format
        String date_string = date_format.format(date);

        // printing date in string
        System.out.println("Date to String : "
                           + date_string);
    }
}
```

**Output**

```java
Date to String : 2020-06-12
```

**方法二:使用**[**simpledate format**](https://www.geeksforgeeks.org/java-simpledateformat-set-1/)**类**

SimpleDateFormat 类用于格式化和解析日期。它有一个内置的 format()方法，可以用多种方式以字符串格式打印日期。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to convert date to string
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.Locale;

public class DateToString {
    public static void main(String[] args)
    {
        // define today's date under date variable
        Date date = new Date();

        // specify the date format to be used
        SimpleDateFormat date_format1 = new SimpleDateFormat("MM/dd/yyyy");

        String date_str = date_format1.format(date);

        System.out.println("MM/dd/yyyy : " + date_str);

        // another date format
        SimpleDateFormat date_format2 = new SimpleDateFormat("dd MMMM yyyy zzzz");

        date_str = date_format2.format(date);

        System.out.println("dd MMMM yyyy zzzz : "
                           + date_str);
    }
}
```

**Output**

```java
MM/dd/yyyy : 11/12/2020
dd MMMM yyyy zzzz : 12 November 2020 Coordinated Universal Time
```

**方法三:使用** [**LocalDate.toString()方法**](https://www.geeksforgeeks.org/localdate-tostring-method-in-java-with-examples/)

1.  从*日期*获取*本地日期*的实例。
2.  使用*本地日期类*的 *toString()方法*将给定日期转换为字符串。
3.  打印结果。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to convert Date to String 

import java.time.LocalDate; 

class GFG { 

    // Function to convert date to string 
    public static String 
    convertDateToString(String date) 
    { 

        // Get an instance of LocalTime 
        // from date 
        LocalDate today = LocalDate.parse(date); 

        // Convert the given date into a 
        // string using toString()method 
        String dateToString 
            = today.toString(); 

        // Return the result 
        return (dateToString); 
    } 

    // Driver Code 
    public static void main(String args[]) 
    { 

        // Given Date 
        String date = "2020-11-13"; 

        // Convert and print the result 
        System.out.print( 
            convertDateToString(date)); 
    } 
}
```

**Output**

```java
2020-11-13
```