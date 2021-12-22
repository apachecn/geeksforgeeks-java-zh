# 在 Java 中，数组列表可以包含对同一个对象的多个引用吗？

> 原文:[https://www . geesforgeks . org/can-an-ArrayList-contain-多次引用-java 中的同一个对象/](https://www.geeksforgeeks.org/can-an-arraylist-contain-multiple-references-to-the-same-object-in-java/)

[Java 中的 ArrayList](https://www.geeksforgeeks.org/arraylist-in-java/) 类基本上是一个可调整大小的数组，也就是说，它可以根据我们在其中添加或移除的值动态地增长和收缩大小。它存在于 [java.util](https://www.geeksforgeeks.org/java-util-package-java/#:~:text=It%20contains%20the%20collections%20framework,the%20Important%20Classes%20in%20Java.) 包中。

我们将讨论一个数组列表是否可以包含对 Java 中同一对象的多个引用。

java 中的 ArrayList 不提供对同一对象的重复引用的检查。因此，我们可以根据需要多次插入同一个对象或对单个对象的引用。如果我们愿意，我们可以借助 [contains()](https://www.geeksforgeeks.org/java-string-contains-method-example/) 方法来检查数组列表中是否已经存在一个元素。

以下是上述问题陈述的代码实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate some functionalities
// of ArrayList

import java.util.ArrayList;

class Employee{
    private String name;
    private String designation;

    // Parameterized constructor for Employee class
    public Employee(String name, String designation) {
        this.name = name;
        this.designation = designation;
    }

    // Creating getters for Employee class
    public String getName() {
        return name;
    }

    public String getDesignation() {
        return designation;
    }
}

public class GFG {
    public static void main(String[] args) {

        // Creating Objects of Employee class
        Employee e1 = new Employee("Raj","Manager");
        Employee e2 = new Employee("Simran", "CEO");
        Employee e3 = new Employee("Anish", "CTO");

        // Creating an ArrayList of Employee type
        ArrayList<Employee> employeeList= new ArrayList<>();

        // Inserting the employee objects in the ArrayList
        employeeList.add(e1);
        employeeList.add(e2);
        employeeList.add(e3);

        // e1 will be inserted again as ArrayList can store multiple
        // reference to the same object
        employeeList.add(e1);

        // Checking if e2 already exists inside ArrayList
        // if it exists then we don't insert it again
        if(!employeeList.contains(e2))
            employeeList.add(e2);

        // ArrayList after insertions: [e1, e2, e3, e1]

        // Iterating the ArrayList with the help of Enhanced for loop
        for(Employee employee: employeeList){
            System.out.println(employee.getName() + " is a " + employee.getDesignation());
        }
    }
}
```

**Output**

```
Raj is a Manager
Simran is a CEO
Anish is a CTO
Raj is a Manager
```