# 将时间戳转换为日期的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到转换-时间戳到日期/](https://www.geeksforgeeks.org/java-program-to-convert-timestamp-to-date/)

[***【日期时间类】***](https://www.geeksforgeeks.org/date-class-java-examples/) 用于在 java 中显示日期和时间并操纵日期和时间，除此之外，它还用于在 java 中格式化日期一个 **d** 时间类跨时区关联数据。所以为了从名为 [*的包中导入这个类*](https://www.geeksforgeeks.org/java-util-package-java/)

时间戳类可以用 java 中的日期类转换成 Java 中的日期类。Util 包。日期类的构造函数接收一个长值作为参数。由于 Date 类的构造函数需要一个长值，我们需要使用 TimeStamp 类的 getTime()方法(存在于 SQL 包中)将 Timestamp 对象转换成一个长值。

> 为了导入日期类语法如下:导入 Java . util . date；

导入该类后，可以创建日期类的对象，以便打印当前日期和时间。现在为了打印默认的日期和时间只需调用打印命令使用 [*toString()*](https://www.geeksforgeeks.org/integer-tostring-in-java/) 方法获取当前的日期和时间

**注意:**为了打印到现在为止的毫秒数，只需使用 [getTime()](https://www.geeksforgeeks.org/java-sql-timestamp-gettime-function-with-examples/) 而不是 to String()来获取程序执行之前的毫秒数。另外，请记住 *01-01-1970* 是基准时间，也称为纪元时间。

**方法:**有以下 3 种方法:

1.  使用构造函数
2.  使用日期参考
3.  使用日历类

**实现:**借助 java 程序单独描述方法:

**方法 1:** 使用日期构造函数将时间戳更新为日期

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert timestamp to Date

// Importing java Date libraries
import java.sql.Timestamp;
import java.util.Date;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Getting the current system time and pasing it
        // to constructor of time-stamp class
        // Using currentTimeMillis
        Timestamp ts
            = new Timestamp(System.currentTimeMillis());

        // Passing the long value in the Date class
        // constructor
        Date date = new Date(ts.getTime());

        // Printing the date
        System.out.println(date);
    }
}
```

**Output**

```
Tue Nov 24 00:28:31 UTC 2020
```

**方法 2:** 使用日期参考从时间戳到日期

时间戳类扩展了日期类。因此，您可以直接将时间戳类的一个实例分配给 Date。在这种情况下，日期对象的输出将像时间戳一样，即它的格式像日期后跟时间(以毫秒为单位)。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert timestamp to Date
// Importing java Date libraries
import java.sql.Timestamp;
import java.util.Date;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Getting the current system time and pasing it
        // to constructor of time-stamp class
        Timestamp ts
            = new Timestamp(System.currentTimeMillis());

        /* Date class is super class of TimeStamp class*/

        //  Directly assigning the object of
        // timestamp class to date class
        Date date = ts;

        // Printing the date
        System.out.println(date);
    }
}
```

**Output**

```
2020-11-24 00:28:30.646
```

**方法 3:** 使用日历类从时间戳到日期

我们还可以使用 calendar 类来获取使用 timestamp 的 date，下面是将 Timestamp 转换为 Date 的方法的实现。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert timestamp to Date

// Importing java Date libraries
import java.sql.Timestamp;
import java.util.Date;
import java.util.Calendar;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Getting the current system time and pasing it
        // to constructor of time-stamp class
        Timestamp timestamp
            = new Timestamp(System.currentTimeMillis());

        // Getting the calendar class instance
        Calendar calendar = Calendar.getInstance();

        // Passing the long value to calendar class function
        calendar.setTimeInMillis(timestamp.getTime());

        // Getting the time using getTime() function
        System.out.println(calendar.getTime());
    }
}
```

**Output**

```
Tue Nov 24 00:28:31 UTC 2020
```