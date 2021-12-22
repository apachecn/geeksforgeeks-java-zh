# 使用 OpenCSV 将 Java Beans 映射到 CSV

> 原文:[https://www . geesforgeks . org/mapping-Java-beans-to-CSV-using-opencsv/](https://www.geeksforgeeks.org/mapping-java-beans-to-csv-using-opencsv/)

将 java bean(Objects)转换为 CSV 文件的需求非常普遍，将 Bean 写入 CSV 文件的方法有很多，但是将 Java Bean 映射到 CSV 的最佳方法之一是使用 OpenCSV 库。在 OpenCSV 中有一个类名*stateflebeantosvbuilder*，它有助于将 Java Beans 转换为 CSV。

1.  第一个任务是**将 OpenCSV 库添加到项目**中。
    *   对于 maven 项目，在 pom.xml 文件中包含 OpenCSV maven 依赖项。

        ```
        <dependency>
            <groupId>com.opencsv</groupId>
            <artifactId>opencsv</artifactId>
            <version>4.1</version>
        </dependency>
        ```

    *   对于 Gradle 项目，包括 OpenCSV 依赖项。

        ```
        compile group: 'com.opencsv', name: 'opencsv', version: '4.1'
        ```

    *   你可以下载 [OpenCSV Jar](https://sourceforge.net/projects/opencsv/files/opencsv/) 并包含在你的项目类路径中。
2.  **将 Java Beans 映射到 CSV**
    下面是将 Java Beans 映射到 CSV 的分步过程。

1.  创建用于将数据写入 CSV 文件的编写器实例。

    ```
    Writer writer = Files.newBufferedWriter(Paths.get(file_location));
    ```

2.  创建需要写入 CSV 文件的对象列表。
3.  使用列位置映射策略将已创建对象的列映射到 csv 的列。
    这是可选步骤。如果未使用 ColumnPositionMappingStrategy，则对象将被写入 csv，列名与对象的属性名相同。

    ```
    ColumnPositionMappingStrategy mappingStrategy = new ColumnPositionMappingStrategy();
        mappingStrategy.setType(Employee.class);

    where Employee is the object to be mapped with CSV.

    ```

4.  创建 stateflebeantosvbuilder 后，通过调用 stateflebeantosvbuilder 类的 build 方法，以 writer 对象为参数，创建*stateflebeantosv*类的对象。根据需要用户也可以提供:

    ```
    StatefulBeanToCsv beanToCsv = new StatefulBeanToCsvBuilder(writer)
    .withMappingStrategy(mappingStrategy)
    . withSeparator('#')
                        .withQuotechar(CSVWriter.NO_QUOTE_CHARACTER)
                        .build();

    ```

    *   *column positionmapping strategy*借助 *withMappingStrategy* 函数的 StatefulBeanToCsvBuilder 对象。
    *   借助*stateflebeantosvbuilder*对象的分离函数*对生成的 csv 文件进行分离。*
    *   借助*stateflebeantosvbuilder*对象的 *withQuotechar* 功能，生成 csv 文件的 *withQuotechar* 。
5.  创建 stateflebeantosv 类的对象后，可以借助 stateflebeantosv 对象的 write 方法将对象或对象列表添加到 Csv 文件中。

    ```
    beanToCsv.write(Employeelist);

    ```

**示例:**在本例中，我们将创建员工对象列表，该列表具有姓名、年龄、公司、工资等属性。然后我们将生成一个包含雇员对象的 CSV 文件 Employees.csv。
代码:

1.  **Employee.java**T3

    ```
    public class Employee {

        public String Name, Age, Company, Salary;

        public Employee(String name, String age, 
                    String company, String salary)
        {
            super();
            Name = name;
            Age = age;
            Company = company;
            Salary = salary;
        }

        @Override
        public String toString()
        {
           return "Employee [Name=" + Name + ", 
           Age=" + Age + ", Company=" + Company + ", 
           Salary=" + Salary + "]";
        }
    }
    ```

    T4】
2.  **BeanToCSV.java**T3

    ```
    import java.io.FileWriter;
    import java.io.Writer;
    import java.nio.*;
    import java.nio.file.Files;
    import java.nio.file.Paths;
    import java.util.*;
    import com.opencsv.bean.ColumnPositionMappingStrategy;
    import com.opencsv.bean.StatefulBeanToCsv;
    import com.opencsv.bean.StatefulBeanToCsvBuilder;

    public class BeanToCSV {
        public static void main(String[] args)
        {

            // name of generated csv
            final String CSV_LOCATION = "Employees.csv ";

            try {

                // Creating writer class to generate
                // csv file
                FileWriter writer = new 
                           FileWriter(CSV_LOCATION);

                // create a list of employee
                List<Employee> EmployeeList = new 
                                     ArrayList<Employee>();
                Employee emp1 = new Employee
                         ("Mahafuj", "24", "HTc", "75000");
                Employee emp2 = new Employee
                      ("Aman", "24", "microsoft", "79000");
                Employee emp3 = new Employee
                        ("Suvradip", "26", "tcs", "39000");
                Employee emp4 = new Employee
                         ("Riya", "22", "NgGear", "15000");
                Employee emp5 = new Employee
                        ("Prakash", "29", "Sath", "51000");
                EmployeeList.add(emp1);
                EmployeeList.add(emp2);
                EmployeeList.add(emp3);
                EmployeeList.add(emp4);
                EmployeeList.add(emp5);

                // Create Mapping Strategy to arrange the 
                // column name in order
                ColumnPositionMappingStrategy mappingStrategy=
                            new ColumnPositionMappingStrategy();
                mappingStrategy.setType(Employee.class);

                // Arrange column name as provided in below array.
                String[] columns = new String[] 
                        { "Name", "Age", "Company", "Salary" };
                mappingStrategy.setColumnMapping(columns);

                // Creating StatefulBeanToCsv object
                StatefulBeanToCsvBuilder<Employee> builder=
                            new StatefulBeanToCsvBuilder(writer);
                StatefulBeanToCsv beanWriter = 
              builder.withMappingStrategy(mappingStrategy).build();

                // Write list to StatefulBeanToCsv object
                beanWriter.write(EmployeeList);

                // closing the writer object
                writer.close();
            }
            catch (Exception e) {
                e.printStackTrace();
            }
        }
    }
    ```

    T4】

**输出**:

```
EmployeeData.csv
CSV file contains:-----

"Mahafuj", "24", "HTc", "75000"
"Aman", "24", "microsoft", "79000"
"Suvradip", "26", "tcs", "39000"
"Riya", "22", "NgGear", "15000"
"Prakash", "29", "Sath", "51000"

```

**参考:**T2】beantosv 官方文档