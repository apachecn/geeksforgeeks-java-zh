# Java 程序使用列的方法获取 JDBC 的列名

> 原文:[https://www . geesforgeks . org/Java-程序使用方法-列获取列名-在 jdbc 中/](https://www.geeksforgeeks.org/java-program-to-use-methods-of-column-to-get-column-name-in-jdbc/)

Java 数据库连接或 JDBC 是一个 Java API(应用程序编程接口)，用于通过 Java 应用程序执行数据库操作。它允许通过 Java 应用程序执行用于创建表和数据操作的 SQL 命令。Java 支持 java.sql 包，该包包含用于访问和处理存储在数据库中的数据的内置方法。java.sql 中的方法抛出 sql 异常，因此代码块必须放在 try 块中，如果有任何异常，则让 catch 块处理异常。

**程序:**

1.  [*for name ()*](https://www.geeksforgeeks.org/class-forname-method-in-java-with-examples/) is a static class method for loading drivers.
2.  Next, use the [*[getconnection ()*](https://www.geeksforgeeks.org/establishing-jdbc-connection-in-java/) method of the DriverManager class to establish a connection to the database. [*getConnection()*](https://www.geeksforgeeks.org/establishing-jdbc-connection-in-java/) Accept the URL, user name and password to establish a connection. The methods defined in the statement are used to interact with the database.
    *   Create a table first, and then insert records into the table.
    *   SQL commands are batched together with [*addbatch ()*](https://www.geeksforgeeks.org/how-to-execute-multiple-sql-commands-on-a-database-simultaneously-in-jdbc/) , and executed at one time with [*Execute batch ()*](https://www.geeksforgeeks.org/how-to-execute-multiple-sql-commands-on-a-database-simultaneously-in-jdbc/) method.
    *   The records in the table are extracted into the result set.
    *   The [*getmetadata ()*](https://www.geeksforgeeks.org/how-to-get-the-datatype-of-a-column-of-a-table-using-jdbc/) method of the ResultSet is used to obtain the metadata of the records extracted into the ResultSet.
    *   The *getcolumncount ()* and *getcolumnname ()* methods of the resultset metadata interface are used to obtain the number of columns in the table and the name of each column.

**例 1:**

## 爪哇

```
// Java Program to Use Methods of Column
// to get column name in JDBC

// Step 1: Importing DB files
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.Statement;

// Class to get columns
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        try {

            // Step 2: Loading and registering drivers

            // Loading driver class
            // using forName() method
            Class.forName("oracle.jdbc.OracleDriver");

            // Step 3: Establishing te connection

            Connection con = DriverManager.getConnection(
                "jdbc:oracle:thin:@localhost:1521:xe",
                "username", "password");
            Statement s = con.createStatement();

            // Step 4: Create a statement
            String sql1
                = "CREATE TABLE ACADEMY(COURSE_ID VARCHAR2(20) PRIMARY KEY, COURSE_NAME VARCHAR2(20),MENTOR VARCHAR2(20),COURSE_FEE NUMBER)";

            // Step 5: Process the query
            // Inserting records in the table
            String sql2
                = "INSERT INTO ACADEMY VALUES('C101','MATH','ROBERT',5000)";
            String sql3
                = "INSERT INTO ACADEMY VALUES('C102','PHYSICS','JANE',8000)";
            String sql4
                = "INSERT INTO ACADEMY VALUES('C103','HISTORY','ADAM',6000)";
            String sql5
                = "INSERT INTO ACADEMY VALUES('C104','BIOLOGY','MARIE',5000)";
            String sql6
                = "INSERT INTO ACADEMY VALUES('C105','ENGLISH','ALBERT',3000)";
            s.addBatch(sql1);
            s.addBatch(sql2);
            s.addBatch(sql3);
            s.addBatch(sql4);
            s.addBatch(sql5);
            s.addBatch(sql6);

            // Step 6: Execute the statements
            // executing the sql commands
            s.executeBatch();

            // Obtaining the resultset
            ResultSet rs
                = s.executeQuery("SELECT * FROM ACADEMY");

            while (rs.next()) {

                System.out.println(
                    rs.getString(1) + "\t\t"
                    + rs.getString(2) + "\t\t"
                    + rs.getString(3) + "\t\t"
                    + rs.getString(4));
            }

            // Retrieving the ResultSetMetadata object
            ResultSetMetaData rsMetaData = rs.getMetaData();
            System.out.println(
                "List of column names in the current table: ");

            // Retrieving the list of column names
            int count = rsMetaData.getColumnCount();

            for (int i = 1; i& lt; = count; i++) {
                System.out.print(rsMetaData.getColumnName(i)
                                 + "\t");
            }

            // Step 7: Close the connection
            con.commit();
            con.close();
        }

        // Catch block to handle exceptions
        catch (Exception e) {

            // Print the exception
            System.out.println(e);
        }
    }
}
```