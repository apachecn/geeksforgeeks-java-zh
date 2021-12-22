# 如何在 Java 应用中设置 Jackson？

> 原文:[https://www . geesforgeks . org/how-setup-Jackson-in-Java-application/](https://www.geeksforgeeks.org/how-to-setup-jackson-in-java-application/)

JSON(Javascript 对象符号)是网络应用程序世界中最流行的数据交换格式。浏览器可以轻松解析 json 请求，并将其转换为 javascript 对象。服务器解析 json 请求，处理它们，并生成新的 json 响应。JSON 是自描述的，容易理解。将 java 对象转换为 json 的过程称为序列化，将 json 转换为 java 对象的过程称为反序列化。

考虑下面的一个示例来了解 json 的文件结构，如下所示:

插图:

我们有一个学生类，有身份、姓名、地址、城市、爱好等属性。让我们理解相应的 json 文件是什么样子，如下所示:

```java
{"id":"S1122","name":"Jane","address":"XYZ Street","city":"Mumbai","hobby":"Badminton, Dancing"}
```

JSON 数据被写成名称/值对，其中名称是属性/属性名称，值是该属性的值。

现在，在为任何 java 应用程序设置 Jackson 之前，让我们讨论一下 Jackson JSON 库。

*   对于 java 应用程序，使用 Json 字符串非常困难。因此，在 java 应用程序中，我们需要一个 json 解析器来解析 Json 文件，并将它们转换成 java 对象。
*   Jackson 就是这样一个 Java Json 库，用于解析和生成 Json 文件。它内置了对象映射器类，该类解析 json 文件并将其反序列化为自定义 java 对象。它有助于从 java 对象生成 json。
*   Jackson 还有一个 Jackson Json Parser 和 Jackson Json Generator，一次解析并生成一个 Json 标记。

**<u>设置:-</u>**

为了在我们的应用程序中使用 Jackson 库，我们需要在 maven 项目的 pom.xml 文件中添加以下依赖项。

```java
<dependency>
   <groupId>com.fasterxml.jackson.core</groupId>
   <artifactId>jackson-core</artifactId>
   <version>2.9.6</version>
</dependency>

<dependency>
   <groupId>com.fasterxml.jackson.core</groupId>
   <artifactId>jackson-annotations</artifactId>
   <version>2.9.6</version>
</dependency>

<dependency>
   <groupId>com.fasterxml.jackson.core</groupId>
   <artifactId>jackson-databind</artifactId>
   <version>2.9.6</version>
</dependency>
```

> 在 pom.xml 中添加这个依赖项时，以下 jar 文件被添加到 eclipse 中的 Maven 依赖项文件夹中:
> 
> *   杰克逊核心 2.9.6.jar
> *   杰克逊-注释-2.9.6.jar
> *   杰克逊数据绑定-2.9.6.jar

> **注意:**如果我们没有使用 maven 项目，那么我们需要在类路径中下载并添加这些 jar 文件。

**实现:**我们来了解一下 Jackson 库是如何解析 json 文件并生成的。

让我们考虑具有姓名、身份证、部门名称、工资、评级等属性的员工类别。我们使用杰克逊库从 Employee 对象生成一个 json 文件。我们更新了它的一个属性——deptName。我们将 employee 对象序列化为 json 文件，然后用 deptName 属性的更新值将其反序列化回 employee 对象。

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
//  Java Program to Illustrate Setting Up of Jackson by
//  parsing Jackson library json files and
//  generating the same

// Importing required classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an employee object with it's attributes
        // set
        Employee employee = getEmployee();
        ObjectMapper mapper = new ObjectMapper();

        // Try block to check for exceptions
        try {

            // Serializes emp object to a file employee.json
            mapper.writeValue(
                new File(
                    "/home/suchitra/Desktop/suchitra/projects/java-concurrency-examples/jackson-parsing/src/main/resources/employee.json"),
                employee);

            // Deserializes emp object in json string format
            String empJson
                = mapper.writeValueAsString(employee);
            System.out.println(
                "The employee object in json format:"
                + empJson);
            System.out.println(
                "Updating the dept of emp object");

            // Update deptName attribute of emp object
            employee.setDeptName("Devops");
            System.out.println(
                "Deserializing updated emp json ");

            // Reading from updated json and deserializes it
            // to emp object
            Employee updatedEmp = mapper.readValue(
                mapper.writeValueAsString(employee),
                Employee.class);

            // Print and display the updated employee object
            System.out.println("Updated emp object is "
                               + updatedEmp.toString());
        }

        // Catch block to handle exceptions

        // Catch block 1
        // Handling JsonGenerationException
        catch (JsonGenerationException e) {

            // Display the exception along with line number
            // using printStackTrace() method
            e.printStackTrace();
        }

        // Catch block 2
        // Handling JsonmappingException
        catch (JsonMappingException e) {

            // Display the exception along with line number
            // using printStackTrace() method
            e.printStackTrace();
        }

        // Catch block 3
        // handling generic I/O exceptions
        catch (IOException e) {

            // Display the exception along with line number
            // using printStackTrace() method
            e.printStackTrace();
        }
    }

    // Method 2
    // To get the employees
    private static Employee getEmployee()
    {
        // Creating an object of Employee class
        Employee emp = new Employee();
        emp.setId("E010890");
        emp.setName("James");
        emp.setDeptName("DBMS");
        emp.setRating(5);
        emp.setSalary(1000000.00);

        // Returning the employee
        return emp;
    }
}

// Class 2
// Helper class
class Employee {

    // Member variables of this class
    private String id;
    private String name;
    private String deptName;
    private double salary;
    private int rating;

    // Member methods of this class
    public String getId() { return id; }
    public void setId(String id) { this.id = id; }
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public String getDeptName() { return deptName; }
    public void setDeptName(String deptName)
    {
        // This keyword refers to current instance
        this.deptName = deptName;
    }

    public double getSalary() { return salary; }
    public void setSalary(double salary)
    {
        this.salary = salary;
    }
    public int getRating() { return rating; }
    public void setRating(int rating)
    {
        this.rating = rating;
    }

    @Override public String toString()
    {
        return "Employee [id=" + id + ", name=" + name
            + ", deptName=" + deptName + ", salary="
            + salary + ", rating=" + rating + "]";
    }
}
```

**输出:**

```java
The employee object in json format:{"id":"E010890","name":"James","deptName":"DBMS","salary":1000000.0,"rating":5}
Updating the dept of emp object
Deserializing updated emp json 
Updated emp object is Employee [id=E010890, name=James, deptName=Devops, salary=1000000.0, rating=5]
```

> 在 src/main/resources 文件夹中，创建了 employee.json。
> 
> ```java
> {"id":"E010890","name":"James","deptName":"DBMS","salary":1000000.0,"rating":5}
> ```

现在让我们进入下一个例子，我们将使用 Jackson 使用对象映射器从 InputStream 中读取一个对象，并将其反序列化为一个 java 对象。

> **注意:**这里我们将在 src/main/resources 文件夹中有一个名为 employee.json 的文件
> 
> ```java
> {"id":"E010890","name":"James","deptName":"DBMS","salary":1000000.0,"rating":5}
> ```

我们将使用[对象映射器类](https://www.geeksforgeeks.org/convert-java-object-to-json-string-using-jackson-api/) *readValue()方法*来读取文件。

```java
ObjectMapper mapper = new ObjectMapper();
InputStream inputStream = new FileInputStream("file-path"); 
Employee emp = mapper.readValue(inputStream, Employee.class);
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
//  Java Program to Illustrate Setting Up of Jackson by
//  Reading an object from an InputStream
// Using Object Mapper & deserializing to object

// Importing required classes
import com.fasterxml.jackson.core.JsonParseException;
import com.fasterxml.jackson.databind.JsonMappingException;
import com.fasterxml.jackson.databind.ObjectMapper;
import java.io.*;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.io.InputStream;

// Class 1
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object mapper instance
        ObjectMapper mapper = new ObjectMapper();

        // Try block to check for exceptions
        try {

            // input stream points to a json file in
            // src/main/resources folder
            InputStream inputStream = new FileInputStream(
                "/home/suchitra/Desktop/suchitra/projects/java-concurrency-examples/jackson-parsing/src/main/resources/employee.json");

            // Deserializes from json file to employee
            // object
            Employee emp = mapper.readValue(inputStream,
                                            Employee.class);
            System.out.println(emp.toString());
        }

        // Catch blocks to handle the exceptions

        // Catch block 1
        // Handling FileNotFoundException
        catch (FileNotFoundException e) {

            // Displaying the exception along with line
            // number using printStackTrace()
            e.printStackTrace();
        }

        // Catch block 2
        catch (JsonParseException e) {

            // Displaying the exception along with line
            // number using printStackTrace()
            e.printStackTrace();
        }

        // Catch block 3
        catch (JsonMappingException e) {
            e.printStackTrace();
        }

        // Catch block 4
        catch (IOException e) {
            e.printStackTrace();
        }
    }
}
}

// Class 2
// Helper class
class Employee {

    // Member variables of this class
    private String id;
    private String name;
    private String deptName;
    private double salary;
    private int rating;

    // Member methods of this class
    public String getId() { return id; }
    public void setId(String id) { this.id = id; }
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public String getDeptName() { return deptName; }
    public void setDeptName(String deptName)
    {
        // This keyword refers to current object itself
        this.deptName = deptName;
    }

    public double getSalary() { return salary; }

    public void setSalary(double salary)
    {
        this.salary = salary;
    }

    public int getRating() { return rating; }

    public void setRating(int rating)
    {
        this.rating = rating;
    }

    @Override public String toString()
    {
        return "Employee [id=" + id + ", name=" + name
            + ", deptName=" + deptName + ", salary="
            + salary + ", rating=" + rating + "]";
    }
}
```

**输出:**

```java
Employee [id=E010890, name=James, deptName=DBMS, salary=1000000.0, rating=5]
```