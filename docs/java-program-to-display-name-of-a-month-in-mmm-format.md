# 以(MMM)格式显示月份名称的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-display-月名-mmm-format/](https://www.geeksforgeeks.org/java-program-to-display-name-of-a-month-in-mmm-format/)

Java 是一种最强大的编程语言，通过它我们可以做很多事情，Java 是一种行业首选语言。所以它有一个巨大的功能领域。这里我们讨论一下 Java 的一个最好的特性，那就是我们如何用简短的形式或者 **MMM** 格式来表示月。

### 使用某些类有两种方法可以做到这一点:

**方法一:使用**[**SimpleDateFormat**](https://www.geeksforgeeks.org/java-simpledateformat-set-1/)**和 Date 类**

*   Here, the **date** class provides the current date and time, while the **simple date format** class uses the date formatted in a certain format, and the month will be displayed in the **mmm** format.
*   The SimpleDateFormat class is located under the **text** package in Java, and the **date** class is located under the **util** package in Java. **Date** The constructor initializes the object with **current date and time** .
*   **Simple dateformat** is a class for formatting and parsing dates.

**示例**

## Java

```java
// Java Program to format the date in MMM
// format using SimpleDateFormat() method

import java.util.Date;
import java.text.SimpleDateFormat;
public class GFG {
    public static void main(String args[])
    {
        // initialize Date class
        Date date = new Date();

        // initialize SimpleDateFormat class
        // it accepts the format of date
        // here it accepts the "MMM" foprmat for month
        SimpleDateFormat month = new SimpleDateFormat("MMM");

        //"format" use to format the date in to string
        String currentMonth = month.format(date);

        System.out.println(currentMonth);
    }
}
```

**输出**

```java
Nov
```