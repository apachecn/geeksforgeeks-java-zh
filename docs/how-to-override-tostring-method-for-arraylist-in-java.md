# 如何在 Java 中覆盖数组列表的 toString 方法？

> 原文:[https://www . geesforgeks . org/how-override-to string-method-for-ArrayList-in-Java/](https://www.geeksforgeeks.org/how-to-override-tostring-method-for-arraylist-in-java/)

java 中的每个类都是 Object 类的直接或间接的子类。 [toString()](https://www.geeksforgeeks.org/object-tostring-method-in-java/) 存在于[对象](https://www.geeksforgeeks.org/object-class-in-java/)类中。toString 方法返回对象的字符串表示形式。toString()可以作为类的一部分被重写，以满足用户的定制需求。每当我们试图打印对象引用时，就会在内部调用 toString()方法。如果我们没有在您的类中定义 toString()方法，那么将调用 Object 类 **toString()** 方法，否则将调用我们实现的/被覆盖的 toString()方法。

**对象类 toString()方法的语法:**

```java
public String toString()
{
    return getClass().getName()+"@"+Integer.toHexString(hashCode());
}
```

**返回:**该方法返回一个字符串。

**示例:**

## Java

```java
// Java program to demonstrate
// how to override toString 
// method for ArrayList

import java.util.ArrayList;

// define a class
class Employee {

    // attributes of an Employee
    private String EmployeeName;
    private int EmployeeId;
    private double EmployeeSalary;

    // Create Constructor that accept
    // name id and salary as
    // an argument
    Employee(String name, int id, double salary)
    {
        this.EmployeeSalary = salary;
        this.EmployeeName = name;
        this.EmployeeId = id;
    }

    // Override toString()
    // provide your own implementation
    public String toString()
    {
        return "   Employee Name = " + this.EmployeeName
            + "    Employee Id = " + this.EmployeeId
            + "    Employee Salary = "
            + this.EmployeeSalary;
    }
}

public class GFG {
    public static void main(String[] args)
    {
        // Create a ArrayList of Employee Class Type
        ArrayList<Employee> ArrList
            = new ArrayList<Employee>();
        ArrList.add(new Employee("Mukul", 1001, 52000.0));
        ArrList.add(new Employee("Robin", 1002, 65000.0));
        ArrList.add(new Employee("Rahul", 1003, 53000.0));
        ArrList.add(new Employee("Suraj", 1004, 45000.0));
        ArrList.add(new Employee("Akash", 1005, 38000.0));

        // When an object is tried to print
        // toString() method is called
        for (Employee t : ArrList) {
            System.out.println(t);
        }
    }
}
```

**输出**

```java
   Employee Name = Mukul    Employee Id = 1001    Employee Salary = 52000.0
   Employee Name = Robin    Employee Id = 1002    Employee Salary = 65000.0
   Employee Name = Rahul    Employee Id = 1003    Employee Salary = 53000.0
   Employee Name = Suraj    Employee Id = 1004    Employee Salary = 45000.0
   Employee Name = Akash    Employee Id = 1005    Employee Salary = 38000.0
```

**说明:**当我们尝试打印 Employee 实例时，调用被覆盖的 toString()方法，并打印字符串值。