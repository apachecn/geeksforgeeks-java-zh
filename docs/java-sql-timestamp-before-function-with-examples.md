# Java SQL Timestamp before()函数示例

> 原文:[https://www . geesforgeks . org/Java-SQL-timestamp-before-function-with-examples/](https://www.geeksforgeeks.org/java-sql-timestamp-before-function-with-examples/)

()之前的**函数是 Java SQL 的 Timestamp 类的一部分。该函数返回一个布尔值，表示时间戳对象是否出现在给定的时间戳对象之前。**

****功能签名:****

```java
public boolean before(Timestamp t)
```

****语法:****

```java
ts1.before(ts2);
```

****参数:**函数接受时间戳对象作为要检查的参数。**

****返回值:**函数返回布尔数据类型，表示 Timestamp 对象是否出现在给定的 Timestamp 对象之前。**

****异常:**函数不抛出任何异常**

****以下示例说明了 before()功能**的使用**

****示例 1:** 创建两个不相等的时间戳，并检查第二个时间戳是否出现在第一个时间戳之前。**

```java
// Java program to demonstrate the
// use of before() function

import java.sql.*;

public class solution {
    public static void main(String args[])
    {

        // Create two timestamp objects
        Timestamp ts1 = new Timestamp(10003);
        Timestamp ts2 = new Timestamp(10001);

        boolean b = ts2.before(ts1);

        // Check if the second timestamp occurs
        // before first timestamp
        if (b) {

            // If true print that the Second Timestamp
            // occurs before the first timestamp
            System.out.println("Second Timestamp occurs"
                               + " before first timestamp");
        }

        else {

            // If false print that the Second Timestamp
            // does not occur before the first timestamp
            System.out.println("Second Timestamp does not occur"
                               + " before first timestamp");
        }
    }
}
```

****输出:**

```java
Second Timestamp occurs before first timestamp

```

**示例 2:** 创建两个相等的时间戳，检查第二个时间戳是否出现在第一个时间戳之前

```java
// Java program to demonstrate the
// use of before() function

import java.sql.*;

public class solution {
    public static void main(String args[])
    {

        // Create two timestamp objects
        Timestamp ts1 = new Timestamp(10000);
        Timestamp ts2 = new Timestamp(10000);

        boolean b = ts2.before(ts1);

        // Check if the second timestamp occurs
        // before first timestamp
        if (b) {

            // If true print that the Second Timestamp
            // occurs before the first timestamp
            System.out.println("Second Timestamp occurs"
                               + " before first timestamp");
        }

        else {

            // If false print that the Second Timestamp
            // does not occur before the first timestamp
            System.out.println("Second Timestamp does not"
                               + " occur before first timestamp");
        }
    }
}
```

**输出:**

```java
Second Timestamp does not occur before first timestamp

```

**参考:**[https://docs.oracle.com/javase/7/docs/api/java/sql/Timestamp.html](https://docs.oracle.com/javase/7/docs/api/java/sql/Timestamp.html)**