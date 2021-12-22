# Java 中的 LinkedBlockingQueue 迭代器()方法

> 原文:[https://www . geeksforgeeks . org/linkedblockingqueue-iterator-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingqueue-iterator-method-in-java/)

LinkedBlockingQueue 的**迭代器()**方法以适当的顺序返回与这个 LinkedBlockingQueue 相同元素的迭代器。从这个方法返回的元素包含了从 LinkedBlockingQueue 的**第一个(头)**到**最后一个(尾)**的所有元素。返回的迭代器弱一致。
**语法:**

```java
public Iterator<E> iterator()
```

**返回值:**该方法按照从第一个(头)到最后一个(尾)的顺序返回与 LinkedBlockingQueue 中存在的元素相同的迭代器。
下面的程序说明了 LinkedBlockingQueue 类的迭代器()方法:
**程序 1:** 从 LinkedBlockingQueue 创建一个迭代器，其中包含一个类的不同学生的名字。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate iterator()
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.Iterator;

public class GFG {

    public static void main(String[] args)
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 7;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<String> linkedQueue
            = new LinkedBlockingQueue<String>(capacityOfQueue);

        // Add element to LinkedBlockingQueue
        linkedQueue.add("John");
        linkedQueue.add("Tom");
        linkedQueue.add("Clark");
        linkedQueue.add("Kat");

        // create Iterator of linkedQueue using iterator() method
        Iterator<String> listOfNames = linkedQueue.iterator();

        // print result
        System.out.println("list of names:");
        while (listOfNames.hasNext())
            System.out.println(listOfNames.next());
    }
}
```

**Output:** 

```java
list of names:
John
Tom
Clark
Kat
```

**程序 2:** 从包含员工列表的 LinkedBlockingQueue 创建迭代器。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate iterator()
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.Iterator;

public class GFG {

    public void collectIterator()
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 7;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Employee> linkedQueue
            = new LinkedBlockingQueue<Employee>(capacityOfQueue);

        // Add element to LinkedBlockingQueue
        Employee emp1 = new Employee("Sachin", "Developer", "39000");
        Employee emp2 = new Employee("Sanjeev", "Tester", "26000");

        // Add Employee Objects to linkedQueue
        linkedQueue.add(emp1);
        linkedQueue.add(emp2);

        // create Iterator of linkedQueue using iterator() method
        Iterator<Employee> listOfEmployee = linkedQueue.iterator();

        // print result from iterator
        System.out.println("list of Employees:");
        while (listOfEmployee.hasNext()) {
            System.out.println("*************************");
            Employee emp = listOfEmployee.next();
            System.out.println("Employee Name : " + emp.name);
            System.out.println("Employee Position : " + emp.position);
            System.out.println("Employee Salary : " + emp.salary);
        }
    }

    // create an Employee Object with name,
    // position and salary as an attribute
    public class Employee {

        public String name;
        public String position;
        public String salary;

        Employee(String name, String position, String salary)
        {
            this.name = name;
            this.position = position;
            this.salary = salary;
        }

        @Override
        public String toString()
        {
            return "Employee [name=" + name + ", position="
                + position + ", salary=" + salary + "]";
        }
    }

    // Main Method
    public static void main(String[] args)
    {
        GFG gfg = new GFG();
        gfg.collectIterator();
    }
}
```

**Output:** 

```java
list of Employees:
*************************
Employee Name : Sachin
Employee Position : Developer
Employee Salary : 39000
*************************
Employee Name : Sanjeev
Employee Position : Tester
Employee Salary : 26000
```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue . html #迭代器–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html#iterator--)