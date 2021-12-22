# Java 中 LinkedBlockingQueue put()方法，示例

> 原文:[https://www . geeksforgeeks . org/linkedblockingqueue-put-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedblockingqueue-put-method-in-java-with-examples/)

如果队列未满，则**链接锁定队列**的 **put(E e)** 方法将作为参数传递的元素插入到该链接锁定队列尾部的方法中。如果队列已满，则此方法将等待空间变得可用，在空间可用后，它将元素插入到 LinkedBlockingQueue 中。

**语法:**

```java
public void put(E e) throws InterruptedException
```

**参数:**该方法采用强制参数 **e** ，即要插入到 LinkedBlockingQueue 中的元素。
**返回值:**该方法不返回任何内容。

**异常:**该方法抛出以下异常:

*   **中断异常**–在等待队列可用时发生中断
*   **空指针异常**–如果传递给方法的元素为空

下面的程序说明了 LinkedBlockingQueue 类的 put(E)方法:

**程序 1:** 使用 put()方法向队列添加新名称后，打印 LinkedBlockingQueue 的元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate put(E e)
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 4;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<String> linkedQueue
            = new LinkedBlockingQueue<String>(capacityOfQueue);

        // Add element using put() method
        linkedQueue.put("Karan");
        linkedQueue.put("Suraj");
        linkedQueue.put("Harsh");
        linkedQueue.put("Rahul");

        // print elements of queue
        System.out.println("Items in Queue are " + linkedQueue);
    }
}
```

**Output:** 

```java
Items in Queue are [Karan, Suraj, Harsh, Rahul]
```

**程序 2:** 在 LinkedBlockingQueue 中使用 put 方法添加 Employee 对象

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate put()
// method of LinkedBlockingQueue

import java.util.Iterator;
import java.util.concurrent.LinkedBlockingQueue;
public class GFG {

    public void PutDemo() throws InterruptedException
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 5;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Employee> linkedQueue
            = new LinkedBlockingQueue<Employee>(capacityOfQueue);

        // Add element to LinkedBlockingQueue
        Employee emp1 = new Employee("Ranjeet", "Tester", "29000", 27);
        Employee emp2 = new Employee("Sanjeet", "Manager", "98000", 34);
        Employee emp3 = new Employee("Karan", "Analyst", "44000", 30);

        // Add Employee Objects to linkedQueue
        // Using put(E e)
        linkedQueue.put(emp1);
        linkedQueue.put(emp2);
        linkedQueue.put(emp3);

        System.out.println("Details of Employees:");
        // print details of linkedQueue
        Iterator itr = linkedQueue.iterator();
        while (itr.hasNext())
            System.out.println(itr.next());
    }

    // create an Employee Object with name,
    // position, salary and age as attributes
    public class Employee {

        public String name;
        public String position;
        public String salary;
        public int Age;
        Employee(String name, String position,
                 String salary, int age)
        {
            this.name = name;
            this.position = position;
            this.salary = salary;
            this.Age = age;
        }
        @Override
        public String toString()
        {
            return "Employee [name=" + name + ", position="
                + position + ", salary=" + salary
                + ", Age=" + Age + "]";
        }
    }

    // Main Method
    public static void main(String[] args)
    {
        GFG gfg = new GFG();
        try {
            gfg.PutDemo();
        }
        catch (InterruptedException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        }
    }
}
```

**Output:** 

```java
Details of Employees:
Employee [name=Ranjeet, position=Tester, salary=29000, Age=27]
Employee [name=Sanjeet, position=Manager, salary=98000, Age=34]
Employee [name=Karan, position=Analyst, salary=44000, Age=30]
```

**程序 3:** 显示 put()方法抛出的 NullPointerException

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate put(E e)
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 4;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<String> linkedQueue
            = new LinkedBlockingQueue<String>(capacityOfQueue);

        // try to put null value in put method
        try {
            linkedQueue.put(null);
        }
        catch (Exception e) {
            // print error details
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:** 

```java
Exception: java.lang.NullPointerException
```

**参考:**T2【https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue . html # put-E-T4】