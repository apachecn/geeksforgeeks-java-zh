# Java 中的 LinkedBlockingQueue peek()方法

> 原文:[https://www . geeksforgeeks . org/linkedblockingqueue-peek-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingqueue-peek-method-in-java/)

LinkedBlockingQueue 的 **peek()** 方法返回 LinkedBlockingQueue 的头。它检索 LinkedBlockingQueue 头的值，但不删除它。如果 LinkedBlockingQueue 为空，则此方法返回 null。

**语法:**

```
public E peek()
```

**返回值:**这个方法返回 LinkedBlockingQueue 的头。

下面的程序说明了 LinkedBlockingQueue 类的 peek()方法:

**程序 1:** 使用 peek()方法返回 LinkedBlockingQueue 的头部，其中容量为 7 的 LinkedBlockingQueue 包含名称列表

```
// Java Program Demonstrate peek()
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
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

        // find head of linkedQueue using peek() method
        String head = linkedQueue.peek();

        // print result
        System.out.println("Queue is " + linkedQueue);

        // print head of queue
        System.out.println("Head of Queue is " + head);

        // removing one element
        linkedQueue.remove();

        // again get head of queue
        head = linkedQueue.peek();

        // print result
        System.out.println("\nRemoving one element from Queue\n");
        System.out.println("Queue is " + linkedQueue);

        // print head of queue
        System.out.println("Head of Queue is " + head);
    }
}
```

**输出:**

```
Queue is [John, Tom, Clark, Kat]
Head of Queue is John

Removing one element from Queue

Queue is [Tom, Clark, Kat]
Head of Queue is Tom

```

**程序 2:** 查找包含员工列表

```
// Java Program Demonstrate peek()
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
public class GFG {

    public void findPeek()
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 7;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Employee> linkedQueue
            = new LinkedBlockingQueue<Employee>(capacityOfQueue);

        // Add element to LinkedBlockingQueue
        Employee emp1 = new Employee("Ravi", "Tester", "39000");
        Employee emp2 = new Employee("Sanjeet", "Manager", "98000");

        // Add Employee Objects to linkedQueue
        linkedQueue.add(emp1);
        linkedQueue.add(emp2);

        // print head then remove element
        // and follow same process again
        // until the queue becomes empty

        while (linkedQueue.size() != 0) {

            // find head of linkedQueue using peek() method
            Employee head = linkedQueue.peek();

            // print results
            System.out.println("Head of list");
            System.out.println("Employee Name : " + head.name);
            System.out.println("Employee Position : " + head.position);
            System.out.println("Employee Salary : " + head.salary);

            linkedQueue.remove();
            if (linkedQueue.size() != 0)
                System.out.println("\nRemoving one element from Queue\n");
        }
    }

    // create an Employee Object with
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
        gfg.findPeek();
    }
}
```

**的 LinkedBlockingQueue 的负责人输出:**

```
Head of list
Employee Name : Ravi
Employee Position : Tester
Employee Salary : 39000

Removing one element from Queue

Head of list
Employee Name : Sanjeet
Employee Position : Manager
Employee Salary : 98000

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue . html # peek–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html#peek--)