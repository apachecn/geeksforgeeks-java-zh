# 如何对 JDBC 的表格内容进行排序？

> 原文:[https://www . geeksforgeeks . org/如何对 jdbc 中的表内容进行排序/](https://www.geeksforgeeks.org/how-to-sort-contents-of-a-table-in-jdbc/)

对表的内容进行排序意味着以有组织的方式重新排列记录，以使数据更有用。您可以通过在表中选择一列来对表中的所有记录进行排序，根据该列对数据进行排序。简单地说，当你对数据排序时，你按照逻辑顺序排列数据。

*   And text and numbers can be sorted in any order, that is, ascending or descending.
*   One or more columns can be sorted at the same time.
*   In SQL, the [order by](https://www.geeksforgeeks.org/sql-order-by/) clause is used to sort the table contents in [JDBC](https://www.geeksforgeeks.org/introduction-to-jdbc/) .
*   By default, some databases sort queries in ascending order. But we can also sort in descending order.
*   We can use the ORDER BY clause for one or more columns at the same time.

**后续步骤:**

1.  Import the necessary libraries.
2.  Register driver class
3.  Connect to your database by providing an address, user name and password.
4.  Create your statement
5.  Write your query.
6.  Execute your query and store the results in the result set.
7.  Show results

```
How ORDER BY works:

   query ----->       select * from Table_Name ORDER BY Column1,Column 2; 

   user table ----->  --------------------------------------------------
                 || id || Name || Age ||
                 ||      1      ||      Prateek  ||     20       ||
                 ||      4      ||      Chhavi   ||     21       ||
                 ||      3      ||      Aman     ||     22       ||
                 ||      2      ||      Kartikay ||     22       ||
                 ||      5      ||      Prakhar  ||    20        ||
                 --------------------------------------------------

   Example 1:         select * from user ORDER BY id;

   Output:           --------------------------------------------------
                 || id || Name || Age ||
                 ||      1      ||      Prateek  ||     20       ||
                 ||      2      ||      Kartikay ||     22       ||
                 ||      3      ||      Aman     ||     22       ||
                 ||      4      ||      Chhavi   ||     21       ||
                 ||      5      ||      Prakhar  ||     20       ||
                 --------------------------------------------------

   Example 2:         select * from user ORDER BY name,age;

   Output:           --------------------------------------------------
                 || id || Name || Age ||
                 ||      3      ||      Aman     ||     22       ||
                 ||      4      ||      Chhavi   ||     21       ||
                 ||      2      ||      Kartikay ||     22       ||     
                 ||      5      ||      Prakhar  ||     20       ||
                 ||      1      ||      Prateek  ||     20       ||
                 --------------------------------------------------
```

**例 1:**

## 爪哇

```
// Java program to sort contents of a table 

import java.sql.*;

public class GFG {

    // driver code
    public static void main(String[] args) throws Exception
    {

        // Register Driver Class
        Class.forName("org.apache.derby.jdbc.ClientDriver");

        // Connection to your database, pass all the
        // necessary parameters such as address , username &
        // password
        Connection con = DriverManager.getConnection();

        // Create Statement
        Statement stmt = con.createStatement();

        // Query to be executed
        String query = "Select * from users ORDER by id";

        // Execute SQL query and store the result in any
        // variable
        ResultSet rs = stmt.executeQuery(query);

        System.out.println("Id    Name    Age");
        while (rs.next()) {
            int id = rs.getInt("id");
            String name = rs.getString("name");
            int age = rs.getInt("age");
            System.out.println(id + "  " + name + "   "
                               + age);
        }

        // close the connection
        con.close();
    }
}
```