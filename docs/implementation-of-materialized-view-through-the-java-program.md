# 通过 Java 程序实现物化视图

> 原文:[https://www . geesforgeks . org/通过 java 程序实现物化视图/](https://www.geeksforgeeks.org/implementation-of-materialized-view-through-the-java-program/)

先决条件: [JDBC](https://www.geeksforgeeks.org/establishing-jdbc-connection-in-java/) 、 [SQL 视图](https://www.geeksforgeeks.org/sql-views/)。

视图只是任何已被赋予名称并保存在数据库中的 SELECT 查询。因此，视图有时被称为命名查询或存储查询。
物化视图是类似于普通视图**的视图，除了一个属性，即它们刷新得更快。**当主表中发生任何更新时，这些视图会自动更新。

假设如果在主表中发生了任何插入，那么物化视图也会得到更新。在下面的程序中，我们试图展示物化视图是如何工作的。每个数据库软件的实际实现可能不同。

```
// Java Program to implementat
// Materialized view
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;
import java.util.Scanner;
import java.sql.PreparedStatement;

public class Materialised_View {
    public static void main(String[] args)
    {
        // Declare connection and resultset objects
        Connection conn;
        ResultSet rs;

        // Declare statement objects
        Statement stmt, stmt1;

        // query to retrieve the details of student table
        String query = "select * from student;";
        Scanner sc = new Scanner(System.in);
        System.out.println("Student Table is Created as Follows:\n");
        System.out.println
              ("*******Student*********\nsid\tsname\taddress\n---- ");
        try {

            // Register the mysql driver
            DriverManager.registerDriver(new com.mysql.jdbc.Driver());

            // get the connection
            conn = DriverManager.getConnection
             ("jdbc:mysql:// localhost:3306/adbms_practicals", "root", "kernel");

            // Initialize the statement object
            stmt = conn.createStatement();

            // execute the query and store the result
            rs = stmt.executeQuery("select * from student;");

            while (rs.next()) {
                // Iterate through the result set and display
                // content of each row of student table.
                System.out.println(rs.getString(1) + "\t" 
                   + rs.getString(2) + "\t" + rs.getString(3));
            }

            System.out.println("\n\nView of this Student Table is As Follows:");
            rs = stmt.executeQuery("select * from Student_Data2;");
            System.out.println
             ("\n***********Student View*******\nsid\tsname\taddress\n-------");
            while (rs.next()) {
                // Iterate through the result set and display
                // content of view of student table.
                System.out.println(rs.getString(1) + "\t" 
                  + rs.getString(2) + "\t" + rs.getString(3));
            }
            while (true) {

                // Perform the operations on table
                System.out.println("Menu:\n1.Insert\n2.Delete\n3.
                 See Changes in View Student_Data2\n4.Exit\nEnter Choice:");

                // take the input from user to insert / delete / see changes
                int ch = sc.nextInt(); 

                int sid;
                String sname = "";
                String address = "";
                switch (ch) {
                case 1:
                    System.out.println("Enter sid:");
                    sid = sc.nextInt();

                    System.out.println("Enter sname:");
                    sname = sc.nextLine();

                    System.out.println("Enter address:");
                    address = sc.nextLine();

                    // create the preparedStatement object and set the values
                    PreparedStatement st3 = conn.prepareStatement
                      ("insert into student values(?, ?, ?);");

                    st3.setInt(1, sid);
                    st3.setString(2, sname);
                    st3.setString(3, address);
                    st3.executeUpdate();

                    // create the preparedStatement object and set the values
                    PreparedStatement st1 = conn.prepareStatement
                        ("insert into Student_Data2 values(?, ?, ?);");

                    st1.setInt(1, sid);
                    st1.setString(2, sname);
                    st1.setString(3, address);
                    st1.executeUpdate(); // execute the preparedStatement to insert row
                    System.out.println("row inserted");

                    break;

                case 2:
                    System.out.println("Enter sid to be deleted:");
                    sid = sc.nextInt();

                    // create the preparedStatement object and set the values
                    PreparedStatement st4 = conn.prepareStatement
                      ("delete from Student_Data2 where sid=?;");
                    st4.setInt(1, sid);

                    PreparedStatement st2 = conn.prepareStatement
                        ("delete from student where sid=?");
                    st2.setInt(1, sid);

                    // execute the preparedStatement to delete row
                    st2.executeUpdate();

                    System.out.println("row deleted");
                    break;

                case 3:
                    System.out.println("\n\nChanges Done in the 
                     Student table also Affects the View Student_Data2");

                    rs = stmt.executeQuery("select * from Student_Data2;");
                    System.out.println
                      ("\n*****Student*******\nsid\tsname\taddress\n--------");
                    while (rs.next()) {

                        // Iterate through the result set and display
                        // recent changes of the table
                            // which got reflected in view.
                            System.out.println(rs.getString(1) + "\t" 
                            + rs.getString(2) + "\t" + rs.getString(3));
                    }
                    break;

                case 4:
                    System.exit(0); // User wants to exit
                    break;
                }
            }
        }
        catch (Exception e) { // catch all exceptions here.
            System.out.println(e);
        }
    }
}
```

输出:

```
Student Table is Created as Follows:
***********Student**************
sid    sname    address
-----------------------------------------------
131    Rohit Pawar    Mumbai
141    Ashish Mane    Pune
152    Sagar Gore    Mumbai
155    Nitesh Chaure    Nagpur
501    Ritesh Dev    Chennai
531    Dev Khire    Delhi

View of this Student Table is As Follows:
***********Student**************
sid    sname    address
-----------------------------------------------
131    Rohit Pawar    Mumbai
141    Ashish Mane    Pune
152    Sagar Gore    Mumbai
155    Nitesh Chaure    Nagpur
501    Ritesh Dev    Chennai
531    Dev Khire    Delhi

Menu:
1.Insert
2.Delete
3.See Changes in View Student_Data2
4.Exit
Enter Choice:1

Enter sid: 123
Enter sname: Amit Kumar
Enter address: Nanded
row inserted

Menu:
1.Insert
2.Delete
3.See Changes in View Student_Data2
4.Exit
Enter Choice:3

Changes Done in the Student table also Affects the View Student_Data2
***********Student**************
sid    sname    address
-----------------------------------------------
131    Rohit Pawar    Mumbai
141    Ashish Mane    Pune
152    Sagar Gore    Mumbai
155    Nitesh Chaure    Nagpur
501    Ritesh Dev    Chennai
531    Dev Khire    Delhi
123    Amit Kumar Nanded

Menu:
1.Insert
2.Delete
3.See Changes in View Student_Data2
4.Exit
Enter Choice:2

Enter sid to be deleted: 123
row deleted

Menu:
1.Insert
2.Delete
3.See Changes in View Student_Data2
4.Exit
Enter Choice:3

Changes Done in the Student table also Affects the View Student_Data2
***********Student**************
sid    sname    address
-----------------------------------------------
131    Rohit Pawar    Mumbai
141    Ashish Mane    Pune
152    Sagar Gore    Mumbai
155    Nitesh Chaure    Nagpur
501    Ritesh Dev    Chennai
531    Dev Khire    Delhi

Menu:
1.Insert
2.Delete
3.See Changes in View Student_Data2
4.Exit
Enter Choice:4

```

**说明:**
输出开始时打印学生表和学生视图。然后，如果用户选择选项 1 将数据插入学生表“123 艾米特·库马尔·南德”中，该新行将被插入该表中。然后用户选择第三个选项来查看学生视图中是否反映了更改，选择第三个选项后，我们可以看到学生视图中也添加了相同的条目。然后，用户选择第二个选项，并给出 sid = 123 作为从学生表中删除条目的输入。类似地，我们可以看到，同样的条目也从学生视图中删除了。这就是刷新实体化视图的工作方式。

请注意，对于每个数据库软件，内部实现可能会有所不同。