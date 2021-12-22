# 如何使用 JDBC API 向表中添加新列？

> 原文:[https://www . geeksforgeeks . org/如何使用 jdbc-api 向表中添加新列/](https://www.geeksforgeeks.org/how-to-add-a-new-column-to-a-table-using-jdbc-api/)

Java 有自己的应用编程接口，使用 JDBC 驱动程序进行数据库连接的 JDBC 应用编程接口。JDBC API 提供了应用程序到 JDBC 的连接，JDBC 驱动程序提供了管理器到驱动程序的连接。

下面是使用 JDBC 将 java 应用程序连接到我们的数据库的 5 个重要步骤。

1.  注册 Java 类
2.  创建连接
3.  创建语句
4.  执行查询
5.  关闭连接

**注意:**将 mysqlconnector.jar 加载到程序中。

**步骤:**

*   从以下链接下载 MySQLConnect/J (JDBC 连接器 jar 文件)[https://dev.mysql.com/downloads/connector/j](https://dev.mysql.com/downloads/connector/j)
*   在**中选择**平台无关**选择操作系统**选项
*   在项目中复制 MySQL-connector-Java-5 . 1 . 34-bin . jar 文件
*   右键单击它，选择构建路径⇾配置构建路径⇾库⇾添加 JARS
*   在 JAR 选择窗口中，选择项目下的 MySQL-connector-Java-5 . 1 . 34-bin . JAR 库
*   单击确定

使用 MySQL cmd 创建一个数据库，添加一个包含记录的表。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to add a column to a table using JDBC

// dont forget to import below package
import java.sql.*;

public class Database {

    // url that points to mysql database,
    // 'db' is database name
    static final String url
        = "jdbc:mysql://localhost:3306/db";

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        try {

            // this Class.forName() method is user for
            // driver registration with name of the driver
            // as argument i have used MySQL driver
            Class.forName("com.mysql.jdbc.Driver");

            // getConnection() establishes a connection. It
            // takes url that points to your database,
            // username and password of MySQL connections as
            // arguments
            Connection conn = DriverManager.getConnection(
                url, "root", "1234");

            // create.Statement() creates statement object
            // which is responsible for executing queries on
            // table
            Statement stmt = conn.createStatement();

            // Executing the query, student is the table
            // name and age is the new column
            String query
                = "ALTER TABLE student ADD COLUMN age INT";

            // executeUpdate() is used for INSERT, UPDATE,
            // DELETE statements.It returns number of rows
            // affected by the execution of the statement
            int result = stmt.executeUpdate(query);

            // if result is greater than 0, it means values
            // has been added
            if (result > 0)
                System.out.println("new column added.");
            else
                System.out.println(
                    "unable to add a column.");

            // closing connection
            conn.close();
        }
        catch (SQLException e) {
            System.out.println(e);
        }
    }
}
```

![Add a new column](img/9f27383f87f2f105f09145bc7f20aa4e.png) ![Output of the table content after adding new column](img/0990dc6bbfe5f55e02c6cfad91d993e9.png)