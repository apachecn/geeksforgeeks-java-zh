# 显示当前日期和时间的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到显示-当前日期和时间/](https://www.geeksforgeeks.org/java-program-to-display-current-date-and-time/)

Java 是一种最强大的编程语言，通过它我们可以做很多事情，Java 是一种行业首选语言。所以它有一个巨大的功能领域。这里我们讨论一下 Java 最好的一个特性，那就是如何用 Java 来表示**当前的日期和时间。**

有很多方法可以做到这一点，有很多类可以显示当前的日期和时间。

**方法 1:使用日期类**

有一个名为 **Date** 的类，可以用 **GMT** 的形式表示当前的日期和时间。我们可以通过在格林尼治时间表上增加 5 小时 30 分钟来获得 **IST** 表。这个类属于 Java 的 **util** 包。

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Display Current Date and Time
import java.util.*;

public class GFG {
    public static void main(String args[])
    {
        Date current_Date = new Date();
        //"Date" class
        //"current_Date" is Date object

        System.out.println(current_Date);
        // print the time and date
    }
}
```

**Output**

```java
Fri Nov 20 07:12:42 UTC 2020

```

使用两个名为**时区的类**将 GMT 格式转换为 IST 格式，这两个类也属于 Java 的 **util** 包和 Java 的**simpleDateformat**包。

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Display Current Date and Time
import java.text.*;
import java.util.*;
public class GFG {
    public static void main(String args[])
    {
        SimpleDateFormat formatDate = new SimpleDateFormat(
            "dd/MM/yyyy  HH:mm:ss z");
        //"SimpleDateForma" class initialize with object
        //"formatDate" this class acceptes the format of
        // date and time as ""dd/MM/yyyy" and "HH:mm:ss z""
        //"z" use for print the time zone

        Date date = new Date();
        // initialize "Date" class

        formatDate.setTimeZone(TimeZone.getTimeZone("IST"));
        // converting to IST or fornmat the Date as IST

        System.out.println(formatDate.format(date));
        // print formatted date and time
    }
}
```

**Output**

```java
20/11/2020  12:42:41 IST

```

**方法二:使用 LocalDateTime 类**

有一个类叫做 **LocalDateTime** 类，也可以用 GMT 的形式表示当前的日期和时间。我们可以通过在格林尼治时间表格上增加 5 小时 30 分钟来获得 IST 表格。这个类属于 Java 的**时间**包。

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Display Current Date and Time
import java.time.*;
public class MyClass {
    public static void main(String args[])
    {
        System.out.println(LocalDateTime.now());
        //"LocalDateTime" is the class
        //"now()" is a method, represent the
        // current date and time
    }
}
```

**Output**

```java
2020-11-20T07:12:43.158549

```

我们可以使用一个名为 **ZonedDateTime** 的类将这个 GMT 形式转换成 IST，它也属于 Java 的 **Time** 包。此类通过指定时区接受时间，并将其转换为特定时区。这里我们将时间转换为**亚洲/加尔各答**形式。

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Display Current Date and Time
import java.util.*;
import java.time.*;
public class GFG {
    public static void main(String[] args)
    {
        Date date = new Date();

        LocalDateTime d = LocalDateTime.now();

        ZonedDateTime UTCtime = d.atZone(ZoneId.of("UTC"));
        //"d" is the current date and
        //"ZonedDateTime" accepts "d" as UTC
        //"atZone" specifies the time zone

        // converting to IST
        ZonedDateTime ISTtime = UTCtime.withZoneSameInstant(
            ZoneId.of("Asia/Kolkata"));
        //"withZoneSameInstant" convert the time
        // to given time zone

        System.out.println(ISTtime);
        // print the time and date
    }
}
```

**Output**

```java
2020-11-20T12:42:42.723246+05:30[Asia/Kolkata]

```

**方法三:使用时钟类**

有一个类叫做 **Clock** 类，也可以用 UTC 的形式表示当前的日期和时间。这个类属于 Java 的**时间**包。

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
/*package whatever //do not write package name here */

import java.time.*;

class GFG {
    public static void main (String[] args)
    {
        System.out.println(Clock.systemUTC().instant());
        //"Clock" is the class 
        //"systemUTC()" is the method which represent the time in UTC form 
    }
}
```

**Output**

```java
2020-11-20T07:12:37.598048Z

```