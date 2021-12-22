# 如何在 JDBC 提交查询？

> 原文:[https://www . geeksforgeeks . org/如何在 jdbc 中提交查询/](https://www.geeksforgeeks.org/how-to-commit-a-query-in-jdbc/)

**COMMIT** 命令用于将任何事务永久保存到数据库中。它用于结束您当前的事务，并使事务中执行的所有更改永久化。事务是一系列 SQL 语句，Oracle 数据库将其视为一个单元。该语句还会擦除[事务](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/sql-transactions/&sa=U&ved=2ahUKEwjg99Sv4ZDtAhVVmuYKHSMEASgQFjAAegQIAhAC&usg=AOvVaw1oDg630otyQkShj46G_LUW)中的所有保存点，并释放事务锁。

当我们使用任何 [DML](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/dml-full-form/&sa=U&ved=2ahUKEwj5q_LU4JDtAhXe7XMBHTvFBHgQFjACegQICBAC&usg=AOvVaw2T2iVgnxpTGd_MiUEO_Wml) 命令如 INSERT、UPDATE 或 DELETE 时，这些命令所做的更改不是永久的，直到当前会话关闭，这些命令所做的更改才能回滚。为了避免这种情况，我们使用 COMMIT 命令将更改标记为永久的。

**使用**[**【JDBC】**](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/introduction-to-jdbc/&sa=U&ved=2ahUKEwjni-bu4JDtAhXk6XMBHfBtB84QFjADegQIBxAC&usg=AOvVaw0o1eGFdteB35SSTn1YkLq3)**API**将我们的 Java 程序连接到 MySQL Server 的 7 个步骤

1.  导入包
2.  加载并注册驱动程序
3.  创建连接
4.  创建声明
5.  执行查询
6.  处理结果
7.  关闭连接

我们还需要在我们的项目中包含 [MySQL 连接器](https://mvnrepository.com/artifact/mysql/mysql-connector-java)。

**提交语法**

```java
COMMIT;

```

**在 SQL 服务器中用于创建相应数据库和表的 SQL 查询**

**创建数据库**

```java
CREATE DATABASE <DataBaseName>; 

```

**当前数据库**

```java
use <DataBaseName>;

```

**在当前数据库中创建一个表**

```java
CREATE TABLE <TableName> (usn int,, name varchar(20)  ,  place varchar (20) );

```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// importing the my sql package
import java.sql.*;

/* The below code cannot generate the output here, since
 * there is no connection between client and mysql server
 *
 * Before running the project in your device
 * make SQL server connection with your project

 * create the respective database/table in sql server
 * in URL write the port number in which your mysql server
 * is running (By default it run in port number 3306)
 */

public class GFG {

    public static void main(String[] args)
    {
        // Database name
        String databaseName = "student";

        // Database URL
        String url
            = "jdbc:mysql://localhost:3306/" + databaseName;

        // Database credentials
        String userName = "root";
        String password = "root";

        Connection con = null;
        Statement st = null;
        ResultSet res = null;
        String query = "";

        try {

            // Register the jdbc driver
            Class.forName("com.mysql.jdbc.Driver");

            // open a connection to database
            con = DriverManager.getConnection(url, userName,
                                              password);

            // set auto commit false
            con.setAutoCommit(false);

            // creating statement
            st = con.createStatement();

            // first let us try to understand , how DB works
            //  without commit statement
            query
                = "INSERT INTO Student values ( 11 , 'Ram' , 'banglore' )";

            // executing query 1 -> adding the above
            // information into the table
            st.executeUpdate(query);
            System.out.println(
                "Inserted row 1 FIRST TIME in the table....");

            query
                = "INSERT INTO Student values ( 22 , 'Shyam' , 'Chennai' )";
            st.executeUpdate(query);
            System.out.println(
                "Inserted row 2 FIRST TIME in the table....");

            // lets , print what we have updated in the table
            query = "Select * from Student ; ";
            res = st.executeQuery(query);

            System.out.println(
                "printing data (without Rollback && without Commit )....");

            while (res.next())
                System.out.print(res.getString("name")
                                 + "   ");
            System.out.println();

            // lets try to rollback (undo the things ,till now we did) 
            // see what difference it will make in the Database
            con.rollback();

            // lets checkout our DB again
            query = "Select * from Student";
            res = st.executeQuery(query);

            System.out.println(
                "printing data (with Rollback && without Commit )....");
            boolean empty = true;

            while (res.next()) {
                empty = false;
                System.out.print(res.getString("name")
                                 + "  ");
            }
            if (empty) {
                System.out.println("Empty table\n\n");
            }

            // Since we haven't commited our transaction ,
            // when we did rollback, everything is gone
            // Now lets ,try with the Commit Statement from
            // begining
            query
                = "INSERT INTO Student values ( 11 , 'Ram' , 'banglore' )";
            st.executeUpdate(query);
            System.out.println(
                "Inserted row 1  SECOND TIME in the table....");

            query
                = "INSERT INTO Student values ( 22 , 'Shyam' , 'Chennai' )";
            st.executeUpdate(query);
            System.out.println(
                "Inserted row 2  SECOND TIME in the table....");

            // now we have committed our transaction
            con.commit();
            System.out.println(
                "committed the transaction successfully....");

            // lets rollback  and like previous lets check
            // what will be left in our database
            con.rollback();
            System.out.println("Done Rollback....");

            query = "Select * from Student";
            res = st.executeQuery(query);

            System.out.println(
                "printing data ( with Commit and then Rollback)....");

            while (res.next())
                System.out.print(res.getString("name")
                                 + "   ");

            System.out.println("\n");
        }
        catch (ClassNotFoundException e) {
            System.out.println("Driver Error");
            e.printStackTrace();
        }
        catch (SQLException e) {
            System.out.println("Connection Error");
            e.printStackTrace();
        }
        catch (Exception e) {
            e.printStackTrace();
        }

        try {

            // Clean-up environment
            if (con != null)
                con.close();
            if (st != null)
                con.close();
            if (res != null)
                res.close();
        }
        catch (Exception e) {

            // Handle errors for JDBC
            System.out.println(e.getMessage());
        }
        finally {
            System.out.println("Thank you .........");
        }
    }
}
```

**输出**

```java
Inserted row 1 FIRST TIME in the table....
Inserted row 2 FIRST TIME in the table....
printing data (without Rollback && without Commit )....
Ram   Shyam    
printing data (with Rollback && without Commit )....
Empty table

Inserted row 1  SECOND TIME in the table....
Inserted row 2  SECOND TIME in the table....
committed the transaction successfully....
Done Rollback....
printing data ( with Commit and then Rollback)....
Ram   Shyam    

Thank you .........

```