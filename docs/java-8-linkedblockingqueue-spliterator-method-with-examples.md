# Java 8 | LinkedBlockingQueue spliterator()方法示例

> 原文:[https://www . geeksforgeeks . org/Java-8-link edblockingqueue-spliterator-method-with-examples/](https://www.geeksforgeeks.org/java-8-linkedblockingqueue-spliterator-method-with-examples/)

**LinkedBlockingQueue** 的**拆分器()**方法返回一个与 LinkedBlockingQueue 元素相同的[拆分器](https://www.geeksforgeeks.org/java-util-interface-spliterator-java8/)。返回的迭代器弱一致。它可以和 Java 8 中的 Streams 一起使用。此外，它还可以单独和批量遍历元素。

**语法:**

```
public Spliterator spliterator()
```

**返回值:**这个方法在 LinkedBlockingQueue 中的元素上返回一个 Spliterator。

下面的程序说明了 LinkedBlockingQueue 类的 spliterator()方法:

**程序 1:** 从 LinkedBlockingQueue 创建一个分割器，该分割器包含一个班级不同学生的名字

```
// Java Program Demonstrate spliterator()
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.*;
public class GFG {

    public static void main(String[] args)
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 7;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<String> linkedQueue
            = new LinkedBlockingQueue<String>(capacityOfQueue);

        // Add element to LinkedBlockingQueue
        linkedQueue.add("Aman");
        linkedQueue.add("Amar");
        linkedQueue.add("Sanjeet");
        linkedQueue.add("Rabi");

        // create Spliterator of linkedQueue
        // using spliterator() method
        Spliterator<String> listOfNames = linkedQueue.spliterator();

        // print result from Spliterator
        System.out.println("list of names:");

        // forEachRemaining method  of Spliterator
        listOfNames.forEachRemaining((n) -> System.out.println(n));
    }
}
```

**输出:**

```
list of names:
Aman
Amar
Sanjeet
Rabi

```

**程序 2:** 从包含员工对象列表的 LinkedBlockingQueue 创建一个拆分器。

```
// Java Program Demonstrate spliterator()
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.*;
public class GFG {

    public void collectSplitator()
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 7;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Employee> linkedQueue
            = new LinkedBlockingQueue<Employee>(capacityOfQueue);

        // Add element to LinkedBlockingQueue
        Employee emp1 = new Employee("Aman", "Blogger", "100000");
        Employee emp2 = new Employee("Amar", "Manager", "99000");

        // Add Employee Objects to linkedQueue
        linkedQueue.add(emp1);
        linkedQueue.add(emp2);

        // create Spliterator of linkedQueue
        // using spliterator() method
        Spliterator<Employee> listOfEmp = linkedQueue.spliterator();

        // print result from Spliterator
        System.out.println("No of Employees = "
                           + linkedQueue.size());

        // forEachRemaining method  of Spliterator
        listOfEmp.forEachRemaining((n) -> print(n));
    }

    // print emplyee details
    public void print(Employee e)
    {
        System.out.println("-----------------------------");
        System.out.println("Employee Name : " + e.name);
        System.out.println("Employee Position : " + e.position);
        System.out.println("Employee Salary : " + e.salary);
    }

    // create an Employee Object with name,
    // position and salary as attributes
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
        gfg.collectSplitator();
    }
}
```

**输出:**

```
No of Employees = 2
-----------------------------
Employee Name : Aman
Employee Position : Blogger
Employee Salary : 100000
-----------------------------
Employee Name : Amar
Employee Position : Manager
Employee Salary : 99000

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue . html # spliterator–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html#spliterator--)