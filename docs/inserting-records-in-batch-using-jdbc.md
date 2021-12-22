# 使用 JDBC

批量插入记录

> 原文:[https://www . geesforgeks . org/insert-records-in-batch-use-JDBC/](https://www.geeksforgeeks.org/inserting-records-in-batch-using-jdbc/)

使用的功能是[*【addBatch()】*](https://www.geeksforgeeks.org/how-to-execute-multiple-sql-commands-on-a-database-simultaneously-in-jdbc/)和[*execute batch()*](https://www.geeksforgeeks.org/how-to-execute-multiple-sql-commands-on-a-database-simultaneously-in-jdbc/)*方法。因为这让我们对 JDBC 车手有了一个初步的了解。因此，为了用 Java 连接到数据库，您需要一个 JDBC 驱动程序。每个数据库(MySQL、Oracle 等。)自带 JDBC 驱动程序，通常由数据库供应商构建，可在数据库网站上找到。考虑到 MySQL 数据库的例子，你需要去 MySQL 网站，下载 MySQL JDBC 驱动程序。jar 文件(也称为 Connector/J)，并将其添加到您的项目中。*

*现在让我们讨论一下他们操作的方法。所以，以上两种方法即 [*addBatch()*](https://www.geeksforgeeks.org/how-to-execute-multiple-sql-commands-on-a-database-simultaneously-in-jdbc/) 和[*execute batch()*](https://www.geeksforgeeks.org/how-to-execute-multiple-sql-commands-on-a-database-simultaneously-in-jdbc/)*方法如下:**

****方法 1:** *添加批次()***

**此方法在内部将参数值添加到批处理中。现在，您可以添加另一组要插入到 SQL 语句中的值。一旦整个批处理被发送到数据库，每组参数都被插入到 SQL 中并单独执行。**

****方法二:**T2【execute batch()**

**调用此方法，该方法执行所有批处理更新。SQL 语句加上参数集一次性发送到数据库。executeBatch()方法返回的 int[]数组是一个 int 数组，它告诉批处理中每个执行的 SQL 语句影响了多少条记录。**

****语法:**创建数据库**

```java
**create table emp(eid varchar(200) unique,ename varchar(200)**
```

****例:****

 **## 爪哇

```java
// Step 1: Importing DB(SQL) classes
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;
import java.sql.Statement;

// Class
public class insertion {

    // Main driver method
    public static void main(String[] args) throws Exception
    {

        // Try block to check for exceptions
        try {
            // Step 2: Loading and registering drivers

            // Loading drivers using forName() method
            Class.forName("com.mysql.jdbc.Driver");

            // Registering driver using DriverManager
            Connection con = DriverManager.getConnection(
                "jdbc:mysql://localhost/test", "root", "");

            // Step 3: Create a statement
            Statement st = con.createStatement();
            String sql
                = "insert into emp (eid,ename) values (?, ?)";

            // Step 4: Execute the query
            PreparedStatement pstmt;
            pstmt = con.prepareStatement(sql);
            final int batchSize = 5000;
            int count = 0;
            for (int i = 4000; i <= 4500; i++) {

                pstmt.setString(1, "181FA0" + i);
                pstmt.setString(2, "181FA0" + i);

                pstmt.addBatch();

                count++;

                if (count % batchSize == 0) {
                    System.out.println("Commit the batch");
                    pstmt.executeBatch();
                }
                pstmt.executeBatch();
            }
        }
        catch (Exception e) {
            System.out.println("Error:" + e.getMessage());
        }
    }
}
```** 

****输出:****

| [oath] | name |
| --- | --- |
| 【181 fa 04001】 | 【181 fa 04001】. | 。。。 |
| 【181 fa 04500】 | 【181 fa 04500】 |