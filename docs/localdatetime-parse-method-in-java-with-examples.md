# Java 中的 LocalDateTime 解析()方法，示例

> 原文:[https://www . geesforgeks . org/local datetime-parse-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-parse-method-in-java-with-examples/)

在 LocalDateTime 类中，根据传递给它的参数，有两种类型的 parse()方法。

### 解析(字符序列文本)

**parse()** 一个 **LocalDateTime** 类的方法，用于从作为参数传递的字符串(如“2018-10-23T17:19:33”)中获取 LocalDateTime 的实例。该字符串必须具有有效的日期时间，并使用日期时间格式化程序进行分析。ISO_LOCAL_DATE_TIME。

**语法:**

```
public static LocalDateTime parse(CharSequence text)

```

**参数:**这个方法只接受一个参数**文本**，也就是在 LocalDateTime 中要解析的文本。它不应为空。

**返回值:**该方法返回**本地日期时间**，即解析后的本地日期时间。

**异常:**如果文本无法解析，该方法抛出**datetime arseeexception**。

下面的程序说明了 parse()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalDateTime.parse() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an LocalDateTime object
        LocalDateTime lt
            = LocalDateTime
                  .parse("2018-12-30T19:34:50.63");

        // print result
        System.out.println("LocalDateTime : "
                           + lt);
    }
}
```

**Output:**

```
LocalDateTime : 2018-12-30T19:34:50.630

```

### 解析(字符序列文本，日期时间格式化程序格式化程序)

**parse()** 一个 **LocalDateTime** 类的方法，用于从字符串(如“2018-10-23T17:19:33”)中获取 LocalDateTime 的实例，该字符串使用特定的格式化程序作为参数传递。使用特定的格式化程序来解析日期时间。

**语法:**

```
public static LocalDateTime parse(CharSequence text, 
                                  DateTimeFormatter formatter)

```

**参数:**这个方法接受两个参数**文本**作为要解析的文本，**格式化程序**作为要使用的格式化程序。

**返回值:**该方法返回**本地日期时间**，即解析后的本地日期时间。

**异常:**如果文本无法解析，该方法抛出**datetime arseeexception**。

下面的程序说明了 parse()方法:
**程序 1:**

```
// Java program to demonstrate
// LocalDateTime.parse() method

import java.time.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a formater
        DateTimeFormatter formatter
            = DateTimeFormatter.ISO_LOCAL_DATE_TIME;

        // create an LocalDateTime object and
        LocalDateTime lt
            = LocalDateTime
                  .parse("2018-12-30T19:34:50.63",
                         formatter);

        // print result
        System.out.println("LocalDateTime : "
                           + lt);
    }
}
```

**Output:**

```
LocalDateTime : 2018-12-30T19:34:50.630

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # parse(Java . lang . charsequence)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#parse(java.lang.CharSequence))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # parse(Java . lang . charsequence，Java . time . format . datetime formatter)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#parse(java.lang.CharSequence, java.time.format.DateTimeFormatter))