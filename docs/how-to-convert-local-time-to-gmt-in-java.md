# Java 中如何将本地时间转换为 GMT？

> 原文:[https://www . geesforgeks . org/如何将本地时间转换为 java 中的 GMT/](https://www.geeksforgeeks.org/how-to-convert-local-time-to-gmt-in-java/)

从 IST 时间或任何标准时间转换为格林尼治时间对于本地人理解和回报他们的国际客户是必要的，如果他们在工作或任何目的方面与海外有联系。今天，我们将看一个代码，其中我们将任何国家的标准时间转换为格林尼治标准时间。

在这里，我们将使用**简单日期格式**来转换格林尼治标准时间中的当地时间。它可以在课堂上获得，如前所述:

```java
java.util.SimpleDateFormat
```

**方法:**可以使用不同的方法，比如 SimpleDateFormat，甚至可能是 *Instance()* 方法。它们是非常简单和有用的方法。我们也可以使用日历和时间方法来这样做。

1.  使用[简单日期格式类](https://www.geeksforgeeks.org/simpledateformat-format-method-in-java-with-examples/)的*格式()*方法
2.  使用[简单日期格式类](https://www.geeksforgeeks.org/simpledateformat-format-method-in-java-with-examples/)的*实例()*方法

**方法 1:** 使用[简单日期格式类](https://www.geeksforgeeks.org/simpledateformat-format-method-in-java-with-examples/)的 f *格式()*方法

Java 中 *DateFormat 类*的 [*format()*](https://www.geeksforgeeks.org/simpledateformat-format-method-in-java-with-examples/) 方法用于将给定日期格式化为日期/时间字符串。基本上**、**方法是将这个日期和时间转换成特定的格式，即 mm/dd/yyyy。

**语法:**

```java
public final String format(Date date)
```

**参数:**该方法取 date 对象类型的一个参数日期，指的是要产生字符串输出的日期。

**返回值:**该方法以 mm/dd/yyyy 的字符串格式返回日期或时间。

**程序:**

*   在这里，我们将简单地首先打印我们的当地时间
*   然后使用简单日期格式将其转换为格林尼治标准时间
*   然后打印两个时区。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to convert local time to GMT

// Importing libraries
// 1\. input output libraries
import java.io.*;
// 3\. Text class
import java.text.DateFormat;
import java.text.SimpleDateFormat;
// 2\. Utility libraries for
// Date and TimeZone class
import java.util.Date;
import java.util.TimeZone;

// Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating a Date class object
        // to take local time from the user
        Date localTime = new Date();

        // Creating a DateFormat class object to
        // convert the localtime to GMT
        DateFormat s = new SimpleDateFormat("dd/MM/yyyy"
                                            + " "
                                            + " HH:mm:ss");

        //  function will helps to get the GMT Timezone
        // using the getTimeZOne() method
        s.setTimeZone(TimeZone.getTimeZone("GMT"));

        // One can get any other time zone also
        // by passing some other argument to it

        // Printing the local time
        System.out.println("local Time:" + localTime);

        // Printing the GMT time to
        // illustrate changes in GMT time
        System.out.println("Time IN Gmt : "
                           + s.format(localTime));
    }
}
```

**Output**

```java
local Time:Thu Feb 04 11:34:15 UTC 2021
Time IN Gmt : 04/02/2021  11:34:15
```