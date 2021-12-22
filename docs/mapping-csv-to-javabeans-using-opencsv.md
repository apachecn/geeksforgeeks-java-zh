# 使用 OpenCSV 将 CSV 映射到 JavaBeans】

> 原文:[https://www . geesforgeks . org/mapping-CSV-to-JavaBean s-using-opencsv/](https://www.geeksforgeeks.org/mapping-csv-to-javabeans-using-opencsv/)

OpenCSV 提供了将 CSV 文件映射到 Java bean 列表的类。CsvToBean 类用于将 CSV 数据映射到 JavaBeans。CSV 数据可以解析成 Bean，但是需要做的是定义映射策略，并将策略传递给 CsvToBean，将数据解析成 bean。HeaderColumnNameTranslateMappingStrategy 是将列 id 映射到 java bean 属性的映射策略。

1.  **首先给项目添加 OpenCSV。**
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
2.  **将 CSV 映射到 JavaBeans**
    将 CSV 映射到 JavaBeans 是一个简单易行的过程。只需遵循以下几个步骤:

1.  Create a Hashmap with mapping between the column id and bean property.

    ```
    Map mapping = new HashMap();
            mapping.put("column  id ", "javaBeanProperty");

    ```

    然后添加 csv 文件的所有列 id 及其对应的 javabean 属性。

2.  创建 HeaderColumnNameTranslateMappingStrategy 对象将映射 hashmap 传递给 setColumnMapping 方法。

    ```
    HeaderColumnNameTranslateMappingStrategy strategy =
     new HeaderColumnNameTranslateMappingStrategy();
            strategy.setType(JavaBeanObject.class);
            strategy.setColumnMapping(mapping);

    ```

3.  创建 CSVReade 和 CsvToBean 类的对象

    ```
    String csvFilename = "data.csv";
    CSVReader csvReader = new CSVReader(new FileReader(csvFilename));
    CsvToBean csv = new CsvToBean();

    ```

4.  调用 CsvToBean 类的解析方法，并传递 HeaderColumnNameTranslateMappingStrategy 和 CSVReader 对象。

    ```
    List list = csv.parse(strategy, csvReader);

    ```

**示例:**让我们将包含学生数据的 csv 文件转换为具有属性名称、卷号、部门、结果、指针的学生对象。

```
StudentData.csv:

name, rollno, department, result, cgpa
amar, 42, cse, pass, 8.6
rohini, 21, ece, fail, 3.2
aman, 23, cse, pass, 8.9
rahul, 45, ee, fail, 4.6
pratik, 65, cse, pass, 7.2
raunak, 23, me, pass, 9.1
suvam, 68, me, pass, 8.2

```

首先创建一个具有属性名称、序号、部门、结果、指针的学生班级。然后创建一个将 csv 数据映射到 JavaBeans 对象的主类。

**节目:**

1.  **Student.java**T3

    ```
    public class Student {
        private static final long serialVersionUID = 1L;

        public String Name, RollNo, Department, Result, Pointer;

        public String getName()
        {
            return Name;
        }

        public void setName(String name)
        {
            Name = name;
        }

        public String getRollNo()
        {
            return RollNo;
        }

        public void setRollNo(String rollNo)
        {
            RollNo = rollNo;
        }

        public String getDepartment()
        {
            return Department;
        }

        public void setDepartment(String department)
        {
            Department = department;
        }

        public String getResult()
        {
            return Result;
        }

        public void setResult(String result)
        {
            Result = result;
        }

        public String getPointer()
        {
            return Pointer;
        }

        public void setPointer(String pointer)
        {
            Pointer = pointer;
        }

        @Override
        public String toString()
        {
            return "Student [Name=" + Name + ", RollNo=" + RollNo + ",
                Department
                = " + Department + ",
                Result = " + Result
                         + ", Pointer=" + Pointer + "]";
        }
    }
    ```

    T4】
2.  **csvtobean.java**T3

    ```
    import java.io.*;
    import java.util.*;

    import com.opencsv.CSVReader;
    import com.opencsv.bean.CsvToBean;
    import com.opencsv.bean.HeaderColumnNameTranslateMappingStrategy;

    public class csvtobean {
        public static void main(String[] args)
        {

            // Hashmap to map CSV data to 
            // Bean attributes.
            Map<String, String> mapping = new 
                          HashMap<String, String>();
            mapping.put("name", "Name");
            mapping.put("rollno", "RollNo");
            mapping.put("department", "Department");
            mapping.put("result", "Result");
            mapping.put("cgpa", "Pointer");

            // HeaderColumnNameTranslateMappingStrategy
            // for Student class
            HeaderColumnNameTranslateMappingStrategy<Student> strategy =
                 new HeaderColumnNameTranslateMappingStrategy<Student>();
            strategy.setType(Student.class);
            strategy.setColumnMapping(mapping);

            // Create castobaen and csvreader object
            CSVReader csvReader = null;
            try {
                csvReader = new CSVReader(new FileReader
                ("D:\\EclipseWorkSpace\\CSVOperations\\StudentData.csv"));
            }
            catch (FileNotFoundException e) {

                // TODO Auto-generated catch block
                e.printStackTrace();
            }
            CsvToBean csvToBean = new CsvToBean();

            // call the parse method of CsvToBean
            // pass strategy, csvReader to parse method
            List<Student> list = csvToBean.parse(strategy, csvReader);

            // print details of Bean object
            for (Student e : list) {
                System.out.println(e);
            }
        }
    }
    ```

    T4】

**输出**:

```
Student [Name=amar, RollNo=42, Department=cse, Result=pass, Pointer=8.6]
Student [Name=rohini, RollNo=21, Department=ece, Result=fail, Pointer=3.2]
Student [Name=aman, RollNo=23, Department=cse, Result=pass, Pointer=8.9]
Student [Name=rahul, RollNo=45, Department=ee, Result=fail, Pointer=4.6]
Student [Name=pratik, RollNo=65, Department=cse, Result=pass, Pointer=7.2]
Student [Name=raunak, RollNo=23, Department=me, Result=pass, Pointer=9.1]
Student [Name=suvam, RollNo=68, Department=me, Result=pass, Pointer=8.2]

```

**参考:** [OpenCSV 文档](http://opencsv.sourceforge.net/)[CSV bean 文档](http://opencsv.sourceforge.net/apidocs/com/opencsv/bean/CsvToBean.html)[mapping strategy](http://opencsv.sourceforge.net/apidocs/com/opencsv/bean/MappingStrategy.html)