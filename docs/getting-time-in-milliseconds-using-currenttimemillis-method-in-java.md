# 使用 Java 中的 currentTimeMillis()方法获取时间(毫秒)

> 原文:[https://www . geeksforgeeks . org/get-time-in-毫秒-using-currentimemillis-method-in-Java/](https://www.geeksforgeeks.org/getting-time-in-milliseconds-using-currenttimemillis-method-in-java/)

在 java 8 之前，编译器通常从 **java.util.*** 包中获取它。但是后来由于日期和时间的使用在每个软件和安卓应用中变得很重要，java 在 java 8 之后开发了日期类。现在已经复制了通过 java.utill 包提供的日期和时间类。Java 在 java 8 版本发布后使用日期和时间类来存储日期和时间。现在，java 通常以一种典型的方式存储日期，比如从 1970 年 1 月 1 日起，以长数据类型存储的毫秒数。因为它存储毫秒，精确时间的准确性增加。

**语法:**获取毫秒

```java
*System.current*TimeMillis();
```

> **注意:**此返回自 1970 年 1 月 1 日 00:00 以来经过的毫秒数，该时间被视为纪元时间。同样，我们可以从毫秒中找出数据的年、月、小时和休息时间。
> 
> ```java
> (System.currentTimeMillis()) / 1000)                           Returns Seconds passed
> (System.currentTimeMillis()) / 1000 / 60)                      Returns Minutes passed
> (System.currentTimeMillis()) / 1000 / 60 / 60);                Returns Hours passed
> (System.currentTimeMillis()) / 1000 / 60 / 60 / 24);           Returns days passed
> (System.currentTimeMillis()) / 1000 / 60 / 60 / 24 / 365);     Returns Years passed
> ```

**实施:**

**E**x**ample**T6

## Java

T9

```java
// Java Program to illustrate TimeMillis() Method

// Importing input output classes
import java.io.*;

// Main Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Note: Whenever the program is run
        // outputs will vary as it is time is real index

        // Print an display commands using
        // curentTimeMillis() method

        // 1\. Printing the Milliseconds passed at particular
        // moment
        System.out.println("Milliseconds : "
                           + System.currentTimeMillis());

        // 2\. Printing the Seconds passed at particular
        // moment
        System.out.println("Seconds : "
                           + (System.currentTimeMillis())
                                 / 1000);

        // 3\. Printing the Minutes passed at particular
        // moment
        System.out.println("Minutes : "
                           + (System.currentTimeMillis())
                                 / 1000 / 60);

        // 4\. Printing the Hours passed at particular moment
        System.out.println("Hours : "
                           + (System.currentTimeMillis())
                                 / 1000 / 60 / 60);

        // 5\. Printing the Days passed at particular moment
        System.out.println("Days : "
                           + (System.currentTimeMillis())
                                 / 1000 / 60 / 60 / 24);

        // 6\. Printing the Years passed at particular moment
        System.out.println("Years : "
                           + (System.currentTimeMillis())
                                 / 1000 / 60 / 60 / 24
                                 / 365);
    }
}
```

T10T12**输出**T1

输出说明:**上述所有输出都是从设定的纪元时间 1970 年 1 月 1 日获得的。**我们现在可以很容易地找到秒，如果我们将毫秒除以 1000，我们将得到自 1970 年 1 月 1 日以来经过的秒数。