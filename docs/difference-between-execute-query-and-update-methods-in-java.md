# Java 中 Execute()、query()和 Update()方法的区别

> 原文:[https://www . geesforgeks . org/Java 中执行查询和更新方法的区别/](https://www.geeksforgeeks.org/difference-between-execute-query-and-update-methods-in-java/)

在开始之前，让我们先了解一下使用以下三个查询参数的参数，如下所示:

*   **布尔执行(字符串 SQL):** 如果可以检索结果集对象，则返回布尔值 true 否则，它返回 false。使用此方法执行 SQL DDL 语句或当您需要使用真正动态的 SQL 时。
*   **int executeUpdate(字符串 SQL):** 返回受 SQL 语句执行影响的行数。使用此方法来执行 SQL 语句，对于这些语句，您预计会有许多行受到影响，例如，INSERT、UPDATE 或 DELETE 语句。
*   **结果集执行查询(字符串 SQL):** 返回结果集对象。当您期望得到一个结果集时，使用这个方法，就像使用 SELECT 语句一样。

**它们以下列方式讨论:**

1.  执行()
2.  执行查询()
3.  执行更新()

**方法 1:** 执行()

*   **描述:**用于所有类型的 SQL 语句的方法，即返回真或假的布尔值。
*   **返回类型:**这个方法返回一个布尔值。真表示查询返回结果集对象，假表示返回整数值或不返回任何内容。
*   **用法:**此方法用于执行选择和非选择查询。
*   **示例**:所有 SQL 语句。

插图:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate usage of execute() Method

// Loading the driver using forName() method 
Class.forName(driver);

// Registering the driver using Drivermanager.getConnection() method 
Connection conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/test",
                  "root", "1234");

// Get database connection
stmt = conn.createStatement();

// Use Connection to create a Statement object

// Execute SQL and return boolean value to 
// indicate whether it contains ResultSet
boolean hasResultSet = stmt.execute(sql);

// Condition holds true till there is a single element 
if (hasResultSet) 
{

    // If there is a ResultSet result set after execution
    rs = stmt.getResultSet();
    // Get the result set

    ResultSetMetaData rsmd = rs.getMetaData();

    // ResultSetMetaData is a metadata interface for analyzing result sets
    int  columnCount = rsmd.getColumnCount();

    // Getting the output ResultSet object
    // with help of object of ResultSet 
    while (rs.next ()) 
    {

        for (int i = 0 ; i < columnCount ; i++ ) 
        {
            System.out.print(rs.getString(i + 1) + "/t");
        }
        System.out.print("/n");
    }
} 
else 
{

    System.out.println ("The records affected by this SQL statement are" 
    + stmt.getUpdateCount () + "Article");
}
```

**方法 2:** 执行查询()

*   **描述:**现在这个方法执行语句，通过从数据库中获取一些数据来返回一个结果集。
*   **用法:**此方法用于执行选择查询。
*   **返回类型:**该方法返回一个结果集对象，该对象包含查询返回的结果。
*   其中一个例子很常见:“选择”

插图:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate execute Query() Method 

// Again first step is to load and register drivers   
Class.forName("com.mysql.jdbc.Driver");

Connection  conn = null;
conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/test",
            "root","root");
// Using DriverManager to get database connection

Statement  stmt = conn.createStatement();
// Use Connection to create a Statement object

// Creating an object of ResultSet class 
ResultSet rs =stmt.executeQuery("select * from teacher");

// Execute the query statement and save the result
// Iterating over elements in above object 
while (rs.next()) 
{

           // Getting the output the query result
           System.out.println(rs.getInt(1) + "/t" +    rs.getString(2));  
}
```

**方法 3:** 执行更新()

*   **说明:**此方法用于执行 DML 语句(INSERT、UPDATE 和 DELETE)，返回 int 值，受影响行的计数。
*   **用法:**此方法用于执行非选择查询。该方法用于执行选择和非选择查询。
*   **返回类型:**表示受查询影响的行数的整数值。对于不返回任何内容的语句，这将是 0。
*   **示例:**

```
DML->INSERT , UPDATE and DELETE
DDL-> CREATE, ALTER
```

插图:

```
  Class.forName("com.mysql.jdbc.Driver");
    // Load the database driver
 Connection  conn = null;
 conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/test",
        "root","1234");
    // Use DriverManager to get database connection
 Statement  stmt = conn.createStatement();
    // Use Connection to create a Statement object

 return stmt.executeUpdate(sql);
    // Execute the DML statement and return the number of records affected
```

> 现在让我们最后总结一下返回类型的差异，如上面的插图所示
> 
> 1.  **execute():** 返回类型为布尔值，表示 ResultSet 是否返回
> 2.  **executeQuery():** Type 方法返回一个 ResultSet，execute 返回查询的结果，常用于执行查询
> 3.  **executeUpdate():** 返回类型为 int，即实现若干行后受影响的 sql 语句，通常用于执行修改语句。