# Java SQL Timestamp setTime()函数示例

> 原文:[https://www . geesforgeks . org/Java-SQL-timestamp-set time-function-with-examples/](https://www.geeksforgeeks.org/java-sql-timestamp-settime-function-with-examples/)

**setTime()**函数是 Java SQL 的 Timestamp 类的一部分。该函数用于设置时间戳对象的时间。该函数以毫秒为单位，表示 1970 年 1 月 1 日之后的时间。

**功能签名:**

```
public void setTime(long t)
```

**语法:**

```
ts1.setTime(l);
```

**参数:**该函数接受长值 **l** 作为参数，该参数将被设置为时间。

**返回值:**函数不返回值。

**异常:**函数不抛出任何异常。

**以下程序说明了 setTime()功能的使用**

**示例 1:** 创建时间戳，并使用 setTime()来更改时间戳对象的时间。

```
// Java program to demonstrate the
// use of setTime() function

import java.sql.*;

public class solution {
    public static void main(String args[])
    {
        // Create two timestamp objects
        Timestamp ts = new Timestamp(10000);

        // Display the timestamp object
        System.out.println("Timestamp time: "
                           + ts.toString());

        // Set the value of timestamp object
        // using setTime function
        ts.setTime(1000000000);

        // Display the new timestamp object
        System.out.println("New Timestamp time: "
                           + ts.toString());
    }
}
```

**Output:**

```
Timestamp time: 1970-01-01 00:00:10.0
New Timestamp time: 1970-01-12 13:46:40.0

```

**示例 2:** 创建一个时间戳，并使用 setTime()通过传递负长值作为参数来更改时间戳对象的时间。给出负长值代表 1970 年 1 月 1 日之前的时间

```
// Java program to demonstrate the
// use of setTime() function

import java.sql.*;

public class solution {
    public static void main(String args[])
    {
        // Create two timestamp objects
        Timestamp ts = new Timestamp(10000);

        // Display the timestamp object
        System.out.println("Timestamp time: "
                           + ts.toString());

        // Set the value of timestamp object
        // using setTime function
        ts.setTime(-1000000000);

        // Display the new timestamp object
        System.out.println("New Timestamp time: "
                           + ts.toString());
    }
}
```

**Output:**

```
Timestamp time: 1970-01-01 00:00:10.0
New Timestamp time: 1969-12-20 10:13:20.0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/SQL/timestamp . html # setTime-long-](https://docs.oracle.com/javase/9/docs/api/java/sql/Timestamp.html#setTime-long-)