# Java SQL Timestamp after()函数示例

> 原文:[https://www . geesforgeks . org/Java-SQL-timestamp-function-after-with-examples/](https://www.geeksforgeeks.org/java-sql-timestamp-after-function-with-examples/)

()后的**函数是 Java SQL 的 Timestamp 类的一部分。该函数返回一个布尔值，表示时间戳对象是否出现在给定的时间戳对象之后。**

****功能签名:****

```
public boolean after(Timestamp t)
```

****语法:****

```
ts1.after(ts2);
```

****参数:**函数接受时间戳对象作为要检查的参数。**

****返回值:**函数返回布尔数据类型，表示时间戳对象是否出现在给定的时间戳对象之后。**

****异常:**函数不抛出任何异常**

****以下示例说明了 after()函数**的使用**

****示例 1:** 创建两个不相等的时间戳，检查第二个时间戳是否出现在第一个时间戳之后**

```
// Java program to demonstrate the
// use of after() function

import java.sql.*;

public class solution {
    public static void main(String args[])
    {

        // Create two timestamp objects
        Timestamp ts1 = new Timestamp(10000);
        Timestamp ts2 = new Timestamp(10001);

        boolean b = ts2.after(ts1);

        // Check if the second timestamp occurs
        // after first timestamp
        if (b) {

            // If true print that the Second Timestamp
            // occurs after the first timestamp
            System.out.println("Second Timestamp occurs"
                               + " after first timestamp");
        }

        else {

            // If false print that the Second Timestamp
            // does not occur after the first timestamp
            System.out.println("Second Timestamp does not"
                               + " occur after first timestamp");
        }
    }
}
```

****输出:**

```
Second Timestamp occurs after first timestamp

```

**示例 2:** 创建两个相等的时间戳，检查第二个时间戳是否出现在第一个时间戳之后

```
// Java program to demonstrate the
// use of after() function

import java.sql.*;

public class solution {
    public static void main(String args[])
    {

        // Create two timestamp objects
        Timestamp ts1 = new Timestamp(10000);
        Timestamp ts2 = new Timestamp(10000);

        boolean b = ts2.after(ts1);

        // Check if the second timestamp occurs
        // after first timestamp
        if (b) {

            // If true print that the Second Timestamp
            // occurs after the first timestamp
            System.out.println("Second Timestamp occurs"
                               + " after first timestamp");
        }
        else {

            // If false print that the Second Timestamp
            // does not occur after the first timestamp
            System.out.println("Second Timestamp does not"
                               + " occur after first timestamp");
        }
    }
}
```

**输出:**

```
Second Timestamp does not occur after first timestamp

```

**参考:**[https://docs.oracle.com/javase/7/docs/api/java/sql/Timestamp.html](https://docs.oracle.com/javase/7/docs/api/java/sql/Timestamp.html)**