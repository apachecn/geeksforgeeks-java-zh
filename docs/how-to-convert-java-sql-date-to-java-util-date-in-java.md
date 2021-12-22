# 如何在 java 中把 java.sql.Date 转换成 java.util.Date？

> 原文:[https://www . geesforgeks . org/how-convert-Java-SQL-date-to-Java-util-date-in-Java/](https://www.geeksforgeeks.org/how-to-convert-java-sql-date-to-java-util-date-in-java/)

如果我们有 SQL 包的日期对象，那么我们可以很容易地将其转换成一个实用的日期对象。在创建 util Date 对象时，我们需要传递[**【getTime()**](https://www.geeksforgeeks.org/date-gettime-method-in-java-with-examples/)方法。

```java
java.util.Date  utilDate = new java.util.Date(sqlDate.getTime());
```

它会给我们一个实用的日期对象。

#### getTime()方法

**语法:**

```java
public long getTime()
```

**参数:**函数不接受任何参数。

**返回值:**返回 1970 年 1 月 1 日 00:00:00 GTM 以来的毫秒数。

**异常:**函数不抛出任何异常。

## 爪哇

```java
// Java program to Convert java.sql.Date to java.util.Date

import java.sql.*;
import java.text.*;
import java.util.*;
public class GFG {

    public static void main(String[] args)
    {

        // sql date object takes time in milliseconds
        long millis = System.currentTimeMillis();

        // creating sql date object
        java.sql.Date sqlDate = new java.sql.Date(millis);

        // creating util date object by passing gettime()
        // method of sql date class
        java.util.Date utilDate = new java.util.Date(sqlDate.getTime());

        DateFormat dateFormat = new SimpleDateFormat("yyyy-MM-dd");

        // converting the util date into string format
        final String stringDate = dateFormat.format(utilDate);

        // printing both dates
        System.out.println("utilDate:" + stringDate);
        System.out.println("sqlDate:" + sqlDate);
    }
}
```

**输出:**

```java
utilDate:2021-01-20
sqlDate:2021-01-20
```