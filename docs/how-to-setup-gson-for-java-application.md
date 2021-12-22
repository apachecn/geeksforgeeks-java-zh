# 如何为 Java 应用设置 GSON？

> 原文:[https://www . geesforgeks . org/how-setup-gson-for-Java-application/](https://www.geeksforgeeks.org/how-to-setup-gson-for-java-application/)

GSON 是谷歌的 JSON 解析器。它用于解析 JSON 文件和生成 JSON 文件。它有多个 API，可以将 Java 对象序列化为 JSON，并将 JSON 文件反序列化为 Java 对象。要在 java 应用程序中使用 GSON，我们首先需要安装它。为此，我们可以在 Maven pom.xml 文件中添加 GSON jar 依赖项，也可以下载 jar 并将其添加到我们的项目中，如下所示:

**pom.xml 文件**如下:

```
<dependency>
    <groupId>com.google.code.gson</groupId>
    <artifactId>gson</artifactId>
    <version>2.3.1</version>
</dependency>
```

让我们理解 Gson 如何使用各种 API 进行序列化和反序列化。

> 考虑一下维护员工信息的 XYZ 公司。因此，我们有员工类，它具有诸如 id、姓名、部门、工资和评级等属性。我们创建一个 Gson 实例，如下所示:
> 
> ```
> Gson gson = new Gson();
> ```

**方法:**

1.  创建一个具有所有属性的对象，并从中生成一个 GSON
2.  使用 GsonBuilder 创建 gson 的新实例

**实施:**

**方法 1:** 我们创建一个具有所有属性的对象，并从中生成一个 GSON。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Create an Employee object with all
// Attributes and generate a GSON out of it

// Importing input output classes
import com.google.gson.Gson;
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of Gson class
        Gson gson = new Gson();
        // Creating an object of Employee class
        Employee emp = new Employee();

        // Attributes
        emp.setName("John");
        emp.setId("E00101");
        emp.setDepartment("IT");
        emp.setSalary(250000.00);
        emp.setRating(7);

        // Generating json from emp object
        String empJson = gson.toJson(emp);
        System.out.println("Emp json is " + empJson);

        // Changing one of the attributes of emp object
        emp.setDepartment("Java");

        // Generating emp object from emp json
        Employee empGenerated = gson.fromJson(
            gson.toJson(emp), Employee.class);

        // Print and display the employee been generated
        System.out.println(
            "Generated employee from json is "
            + empGenerated);
    }
}

// Class 2
// Helper class
class Employee {

    // Member variables of this class
    private String id;
    private String name;
    private String department;
    private int rating;
    private double salary;

    // Member functions of this class

    // Method 1
    public String getId() { return id; }

    // Method 2
    public void setId(String id) { this.id = id; }

    // Method 3
    public String getName() { return name; }

    // Method 4
    public void setName(String name) { this.name = name; }

    // Method 5
    public String getDepartment() { return department; }

    // Method 6
    public void setDepartment(String department)
    {
        this.department = department;
    }

    // Method 7
    public int getRating() { return rating; }

    // Method 8
    public void setRating(int rating)
    {
        this.rating = rating;
    }

    // Method 9
    public double getSalary() { return salary; }

    // Method 10
    public void setSalary(double salary)
    {
        this.salary = salary;
    }

    // Method  11
    @Override public String toString()
    {
        return "Employee [id=" + id + ", name=" + name
            + ", department=" + department + ", rating="
            + rating + ", salary=" + salary + "]";
    }
}
```

**输出:**

```
Emp json is {"id":"E00101","name":"John","department":"IT","rating":7,"salary":250000.0}
Generated employee from json is Employee [id=E00101, name=John, department=Java, rating=7, salary=250000.0]
```

**方法 2:** 我们还可以使用 GsonBuilder 创建 gson 的新实例。

**语法:**

```
GsonBuilder gsonBuilder = new GsonBuilder();
Gson gson = gsonBuilder.create();
```

**实施:**

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program where we will be using GsonBuilder object to
// Pretty Print the gson Contents

// Importing I/O classes
import java.io.*;

// Class 1
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of Employee class
        Employee emp = new Employee();

        // Attributes
        emp.setId("F000101");
        emp.setName("Dave");
        emp.setRating(9);
        emp.setDepartment("DB");
        emp.setSalary(150000.00);

        // Creating a GSON builder
        GsonBuilder gsonBuilder = new GsonBuilder();

        // Creating a GSON from GSON builder
        Gson gson = gsonBuilder.create();

        // Creating an employee gson using pretty printing
        String empJson = gsonBuilder.setPrettyPrinting()
                             .create()
                             .toJson(emp);

        // Print and display
        System.out.println(
            "Emp json in pretty print format:" + empJson);

        // Update rating of emp object
        emp.setRating(8);

        Employee updatedEmp = gson.fromJson(
            gson.toJson(emp), Employee.class);

        // Print and displaying the updated employee
        System.out.println("Updated employee is : "
                           + updatedEmp);
    }
}

// Class 2
// Helper class
class Employee {

    // Attributes
    private String id;
    private String name;
    private String department;
    private int rating;
    private double salary;

    // Member methods of this class
    public String getId() { return id; }

    public void setId(String id) { this.id = id; }

    public String getName() { return name; }

    public void setName(String name) { this.name = name; }

    public String getDepartment() { return department; }

    public void setDepartment(String department)
    {
        this.department = department;
    }

    public int getRating() { return rating; }

    public void setRating(int rating)
    {
        this.rating = rating;
    }

    public double getSalary() { return salary; }

    public void setSalary(double salary)
    {
        this.salary = salary;
    }

    @Override public String toString()
    {
        return "Employee [id=" + id + ", name=" + name
            + ", department=" + department + ", rating="
            + rating + ", salary=" + salary + "]";
    }
}
```

```
Output:-
Emp json in pretty print format:{
  "id": "F000101",
  "name": "Dave",
  "department": "DB",
  "rating": 9,
  "salary": 150000.0
}
Updated employee is : Employee [id=F000101, name=Dave, department=DB, rating=8, salary=150000.0]
```

> 如果我们将 Employee 类中的任何字段设置为瞬态的，那么 Gson 库将在序列化和反序列化期间忽略它，并将其设置为默认值。让我们用一个例子来理解这一点。

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Make Rating Attribute of Employee class
// as Transient

// Importing required classes
import java.io.*;

// Class 1
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of Gson and user-defined
        // Employee class
        Gson gson = new Gson();
        Employee emp = new Employee();

        emp.setName("Jane");
        emp.setId("J01012");
        emp.setDepartment("Devops");
        emp.setSalary(200000.00);
        emp.setRating(7);

        // Generating json from emp object
        String empJson = gson.toJson(emp);
        System.out.println("Emp json is " + empJson);

        // Changing one of the attributes of emp object
        emp.setDepartment("Java");

        // Generate emp object from emp json
        Employee empGenerated = gson.fromJson(
            gson.toJson(emp), Employee.class);

        // Print and display the employee generated from
        // json
        System.out.println(
            "Generated employee from json is "
            + empGenerated);
    }
}

// Class 2
// Helper class
class Employee {

    // Attributes
    private String id;
    private String name;
    private String department;
    private transient int rating;
    private double salary;

    // Member methods of this class

    public String getId() { return id; }

    public void setId(String id) { this.id = id; }

    public String getName() { return name; }

    public void setName(String name) { this.name = name; }

    public String getDepartment() { return department; }

    public void setDepartment(String department)
    {
        this.department = department;
    }

    public int getRating() { return rating; }

    public void setRating(int rating)
    {
        this.rating = rating;
    }

    public double getSalary() { return salary; }

    public void setSalary(double salary)
    {
        this.salary = salary;
    }

    @Override public String toString()
    {
        return "Employee [id=" + id + ", name=" + name
            + ", department=" + department + ", rating="
            + rating + ", salary=" + salary + "]";
    }
}
```

**输出:**

```
Emp json is {"id":"J01012","name":"Jane","department":"Devops","salary":200000.0}
Generated employee from json is Employee [id=J01012, name=Jane, department=Java, rating=0, salary=200000.0]
```

输出解释:

当 employee 对象序列化为 json 时，评级属性不会出现在 json 字符串中，因为它被标记为瞬态。当 json 字符串被反序列化为 employee 对象时，作为 int 字段的评级被设置为默认值 0。因此，Gson 库会忽略瞬态字段，并根据字段的数据类型将其设置为默认值。