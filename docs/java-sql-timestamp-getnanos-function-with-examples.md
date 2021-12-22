# Java SQL Timestamp getNanos()函数示例

> 原文:[https://www . geesforgeks . org/Java-SQL-timestamp-getnano-function-with-examples/](https://www.geeksforgeeks.org/java-sql-timestamp-getnanos-function-with-examples/)

**getNanos()** 函数是 Java SQL 的 Timestamp 类的一部分。该函数用于获取时间戳对象的秒值的小数部分。该函数返回对象的 nanos 值。

**功能签名:**

```java
public int getNanos()
```

**语法:**

```java
ts1.getNanos();
```

**参数:**函数不接受任何参数。

**返回值:**该函数返回一个整数值，即对象的纳米值

**异常:**函数不抛出任何异常

**下面的例子说明了 getNanos()函数的使用**

**示例 1:** 创建一个时间戳，并使用 getNanos()获取时间戳对象的小数部分。

```java
// Java program to demonstrate the
// use of getNanos() function

import java.sql.*;

public class solution {
    public static void main(String args[])
    {

        try {

            // Create two timestamp objects
            Timestamp ts = new Timestamp(10000);

            // Display the timestamp object
            System.out.println("Timestamp time : "
                               + ts.toString());

            // Set the value of the fractional part
            // of timestamp object
            // using setNanos function
            ts.setNanos(1000000);

            // Display the timestamp object's
            // seconds' fractional part
            System.out.println("New Timestamp time : "
                               + ts.toString());
            System.out.println(" Fractional Part :"
                               + ts.getNanos());
        }

        catch (IllegalArgumentException e) {

            // Display the error if any error has occured
            System.err.println(e.getMessage());
        }
    }
}
```

**输出:**

```java
Timestamp time : 1970-01-01 00:00:10.0
New Timestamp time : 1970-01-01 00:00:10.001
 Fractional Part :1000000

```

**示例 2:** 创建时间戳，使用 getNanos()获取时间戳对象的小数部分，不要设置任何秒的小数

```java
// Java program to demonstrate the
// use of getNanos() function

import java.sql.*;

public class solution {
    public static void main(String args[])
    {

        try {

            // Create two timestamp objects
            Timestamp ts = new Timestamp(10000);

            // Display the timestamp object
            System.out.println("Timestamp time : "
                               + ts.toString());

            // Display the timestamp object's
            // seconds' fractional part
            System.out.println("Fractional Part : "
                               + ts.getNanos());
        }

        catch (IllegalArgumentException e) {

            // Display the error if any error has occured
            System.err.println(e.getMessage());
        }
    }
}
```

**输出:**

```java
Timestamp time : 1970-01-01 00:00:10.0
Fractional Part : 0

```

**参考:**[https://docs.oracle.com/javase/7/docs/api/java/sql/Timestamp.html](https://docs.oracle.com/javase/7/docs/api/java/sql/Timestamp.html)