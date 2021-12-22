# Java 中的 DateFormat 格式(Date obj)方法

> 原文:[https://www . geesforgeks . org/dateform-format date-obj-method-in-Java/](https://www.geeksforgeeks.org/dateformat-formatdate-obj-method-in-java/)

Java 中 DateFormat 类的 format()方法用于将给定的 Date 对象格式化为表示日期/时间的字符串。

**语法** :

```java
String format(Date date)

```

**参数**:该方法接受单个参数*日期*，这是一个日期对象。

**返回值**:该方法返回一个字符串，该字符串是作为参数传递给该方法的 date 对象的格式化日期时间值。

下面的程序说明了上述方法:

**程序 1** :

```java
// Java program to illustrate the
// format() method

import java.text.DateFormat;
import java.util.Date;

public class GFG {
    public static void main(String[] args)
    {
        // Create a Date instance
        Date currentDate = new Date();

        // Create a DateFormat instance and format
        // current Date
        String dateToStr = DateFormat.getInstance()
                               .format(currentDate);

        System.out.println("Formatted Date String: "
                           + dateToStr);
    }
}
```

**输出:**

```java
Formatted Date String: 2/27/19 3:31 PM

```

**程序二** :

```java
// Java program to illustrate the
// format() method

import java.text.DateFormat;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create a Date instance
        Date date = new Date(2323223232L);

        // Create a DateFormat instance and format
        // the specified Date
        String dateToStr = DateFormat.getInstance()
                               .format(date);

        System.out.println("Formatted Date String: "
                           + dateToStr);
    }
}
```

**输出:**

```java
Formatted Date String: 1/27/70 9:20 PM

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/dateformat . html # format(Java . util . date)](https://docs.oracle.com/javase/7/docs/api/java/text/DateFormat.html#format(java.util.Date))\