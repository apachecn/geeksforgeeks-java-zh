# 如何在 java 中把 java.util.Date 转换成 java.sql.Date？

> 原文:[https://www . geesforgeks . org/how-convert-Java-util-date-to-Java-SQL-date-in-Java/](https://www.geeksforgeeks.org/how-to-convert-java-util-date-to-java-sql-date-in-java/)

日期类存在于 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)和 [java.sql 包](https://www.geeksforgeeks.org/tag/java-sql-package/)中。尽管两个包的类名相同，但它们的实用程序不同。java.util 包的 DATE 类在 java 应用程序中需要数据来做任何计算或其他各种事情时是必需的，而 java.sql 包的 date 类在我们需要存储或读取 sql 中的 Date 类型的数据时使用，同样 java.sql 包的 Date 类只存储关于日期的信息，而 java.util 包的 Date 类存储日期和时间信息。

必须记住，当我们需要将一种数据形式转换为另一种数据形式时，必须使用 java.util 包的 Date 类的[*【getTime()】*方法](https://www.geeksforgeeks.org/date-gettime-method-in-java-with-examples/)。虽然 java.sql.Date 类是 java.util.Date 类的子类，但是我们不能在任何必须传递 *java.util.Date* 类的地方使用 java.sql.Date 类，否则会违反 [Liskov 替换原则](https://www.geeksforgeeks.org/an-introduction-to-software-development-design-principles/)，我们的程序在执行时会抛出运行时错误，因此不建议将 SQL Date 传递给期望使用 util date 的方法。让我们先讨论 getTime()方法，然后再讨论实现部分。

**Java Date 类**的 **getTime()** 方法返回自 1970 年 1 月 1 日 00:00:00 GTM 以来的毫秒数，由 Date 对象表示。

**语法:**

```java
public long getTime()
```

**参数:**函数不接受任何参数。

**返回值:**返回 1970 年 1 月 1 日 00:00:00 GTM 以来的毫秒数。

**异常:**函数不抛出任何异常。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert java.sql.Date to java.util.Date

// Importing utility package
// Importing SQL package
import java.sql.*;
import java.util.*;

// Main Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Date class of Util package contains both date and
        // time information
        java.util.Date utilPackageDate
            = new java.util.Date();

        // Print and display the utility package date in
        // java
        System.out.println("Util Package date in Java is : "
                           + utilPackageDate);

        // Date class of sql package contains only date
        // information without time
        java.sql.Date sqlPackageDate
            = new java.sql.Date(utilPackageDate.getTime());

        // Print ann display the SQL java package
        System.out.println("SQL Package  date in Java : "
                           + sqlPackageDate);
    }
}
```

**Output**

```java
Util Package date in Java is : Wed Mar 17 11:56:06 UTC 2021
SQL Package  date in Java : 2021-03-17

```

> **注意:**上述日期和时间是在程序编译运行时获取的。它将随着时间的推移而变化，其中时间计算的基线是历元时间