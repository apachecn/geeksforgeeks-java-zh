# Java SQL Timestamp getTime()函数示例

> 原文:[https://www . geesforgeks . org/Java-SQL-timestamp-gettime-function-with-examples/](https://www.geeksforgeeks.org/java-sql-timestamp-gettime-function-with-examples/)

**getTime()** 函数是 Java SQL 的 Timestamp 类的一部分。该函数用于获取时间戳对象的时间。该函数返回以毫秒为单位的时间，表示 1970 年 1 月 1 日之后的时间(以毫秒为单位)。

**功能签名:**

```
public long getTime()
```

**语法:**

```
ts1.getTime();
```

**参数:**该功能不需要任何参数。

**返回值:**函数返回代表时间的长值，单位为毫秒。

**异常:**函数不抛出任何异常。

**下面的例子说明了 getTime()函数的使用**

**示例 1:** 创建一个时间戳，使用 getTime()获取时间戳对象的时间。

```
// Java program to demonstrate the
// use of getTime() function

import java.sql.*;

class GFG {
    public static void main(String args[])
    {
        // Create two timestamp objects
        Timestamp ts = new Timestamp(10000);

        // Display the timestamp object
        System.out.println("Timestamp time : "
                           + ts.toString());
        System.out.println("Time in milliseconds : "
                           + ts.getTime());
    }
}
```

**输出:**

```
Timestamp time : 1970-01-01 00:00:10.0
Time in milliseconds : 10000

```

**示例 2:** 创建时间戳，使用 getTime()获取时间戳对象的时间，并将时间设置在 1970 年 1 月 1 日之前。负长值代表 1970 年 1 月 1 日之前的时间

```
// Java program to demonstrate the
// use of getTime() function

import java.sql.*;

public class solution {
    public static void main(String args[])
    {

        // Create two timestamp objects
        Timestamp ts = new Timestamp(-10000);

        // Display the timestamp object
        System.out.println("Timestamp time : "
                           + ts.toString());

        System.out.println("Time in milliseconds : "
                           + ts.getTime());
    }
}
```

**输出:**

```
Timestamp time : 1969-12-31 23:59:50.0
Time in milliseconds : -10000

```

**参考:**[https://docs.oracle.com/javase/7/docs/api/java/sql/Timestamp.html](https://docs.oracle.com/javase/7/docs/api/java/sql/Timestamp.html)