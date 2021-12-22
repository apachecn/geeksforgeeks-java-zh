# Java 中 BlockingQueue take()方法示例

> 原文:[https://www . geeksforgeeks . org/blocking queue-take-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingqueue-take-method-in-java-with-examples/)

**阻塞队列**接口的 **take()** 方法用于检索和删除该队列的头。如果队列是空的，那么它将等待直到一个元素变得可用。如果在线程上工作并在该进程中使用阻塞队列，该方法会更有效。因此，如果没有可用的元素，最初调用 take()的线程将进入睡眠状态，让其他线程做它们需要做的任何事情。

**语法:**

```java
public E take() throws InterruptedException
```

**返回值:**这个方法在这个阻塞队列的头部返回值。如果队列是空的，那么它将等待直到一个元素变得可用。
**异常:**此方法抛出以下异常:

*   **中断异常**–如果队列为空，在等待元素变为可用时发生中断。

**注**:**封锁队列**的 **take()** 方法继承了 Java 中的**队列**类。
以下程序举例说明了 BlockingQueue 接口的 take()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate take()
// method of BlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;
public class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of BlockingQueue
        int capacityOfQueue = 4;

        // create object of BlockingQueue
        BlockingQueue<String> BQ
            = new LinkedBlockingQueue<String>(capacityOfQueue);

        // Add element to BlockingQueue
        BQ.add("Ravi");
        BQ.add("Suraj");
        BQ.add("Harsh");
        BQ.add("Sayan");

        // print elements of queue
        System.out.println("Items in Queue are " + BQ);

        // remove two elements from queue from head
        // Applying take() method on queue to remove element
        String removedItem1 = BQ.take();

        // print removedItem and queue
        System.out.println("Removed Item from head is "
                           + removedItem1);

        // print elements of queue after removing first item
        System.out.println("Remaining Items in Queue are "
                           + BQ);

        // Applying take() method on queue to remove another element
        String removedItem2 = BQ.take();

        // print removedItem and queue
        System.out.println("Removed Item from head is "
                           + removedItem2);

        // print elements of queue after removing first item
        System.out.println("Remaining Items in Queue are "
                           + BQ);
    }
}
```

**Output:** 

```java
Items in Queue are [Ravi, Suraj, Harsh, Sayan]
Removed Item from head is Ravi
Remaining Items in Queue are [Suraj, Harsh, Sayan]
Removed Item from head is Suraj
Remaining Items in Queue are [Harsh, Sayan]
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate take()
// method of BlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;

public class GFG {

    public void takeDemo() throws InterruptedException
    {
        // define capacity of BlockingQueue
        int capacityOfQueue = 5;

        // create object of BlockingQueue
        BlockingQueue<Employee> BQ
            = new LinkedBlockingQueue<Employee>(capacityOfQueue);

        // Add element to BlockingQueue
        Employee emp1 = new Employee("Ravi", "Tester", "39000");
        Employee emp2 = new Employee("Sanjeet", "Manager", "98000");

        // Add Employee Objects to BQ
        BQ.add(emp1);
        BQ.add(emp2);

        // remove elements from the queue
        // and follow this process again and again
        // until the queue becomes empty
        while (BQ.size() != 0) {

            // Remove Employee item from BlockingQueue
            // using take()
            Employee removedEmp = BQ.take();

            // print removedItem
            System.out.println("Removed Item is :");
            System.out.println("Employee Name - "
                               + removedEmp.name);
            System.out.println("Employee Position - "
                               + removedEmp.position);
            System.out.println("Employee Salary - "
                               + removedEmp.salary);

            // find size of BQ
            int size = BQ.size();

            // print remaining capacity value
            System.out.println("\nSize of list :" + size + "\n");
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
        try {
            gfg.takeDemo();
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**Output:** 

```java
Removed Item is :
Employee Name - Ravi
Employee Position - Tester
Employee Salary - 39000

Size of list :1

Removed Item is :
Employee Name - Sanjeet
Employee Position - Manager
Employee Salary - 98000

Size of list :0
```