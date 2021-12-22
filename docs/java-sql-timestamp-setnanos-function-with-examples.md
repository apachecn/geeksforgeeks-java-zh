# Java SQL Timestamp setNanos()函数示例

> 原文:[https://www . geesforgeks . org/Java-SQL-timestamp-set nano-function-with-examples/](https://www.geeksforgeeks.org/java-sql-timestamp-setnanos-function-with-examples/)

**setNanos()** 函数是 Java SQL 的 Timestamp 类的一部分。该函数用于设置时间戳对象第二个值的小数部分。该函数将对象的纳米值设置为给定值。
**功能签名:**

```
public void setNanos(int t)
```

**语法:**

```
ts1.setNanos(l);
```

**参数:**函数接受 int 值 **t** 作为参数，该参数是要设置的纳秒值。
**返回值:**函数不返回值。
**异常:**如果传递的参数小于 0 或大于 9999999999
**则函数抛出**IllegalArgumentException**以下示例说明了 setNanos()函数的使用**
**示例 1:** 创建时间戳并使用 setNanos()设置时间戳对象的小数部分。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the
// use of setNanos() function

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

            // Display the new timestamp object
            System.out.println("New Timestamp time : "
                               + ts.toString());
        }

        catch (IllegalArgumentException e) {

            // Display the error if any error has occured
            System.err.println(e.getMessage());
        }
    }
}
```

**Output:** 

```
Timestamp time : 1970-01-01 00:00:10.0
New Timestamp time : 1970-01-01 00:00:10.001
```