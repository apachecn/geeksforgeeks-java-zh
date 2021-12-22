# Java 中的 BlockingQueue put()方法，带示例

> 原文:[https://www . geeksforgeeks . org/blocking queue-put-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingqueue-put-method-in-java-with-examples/)

如果队列未满，则**阻塞队列**接口的 **put(E e)** 方法将作为参数传递的元素插入到该阻塞队列尾部的方法中。如果队列已满，则此方法将等待空间变得可用，在空间可用后，它将元素插入到 BlockingQueue 中。

**语法:**

```java
public void put(E e) throws InterruptedException
```

**参数:**该方法采用强制参数 **e** ，即要插入到 LinkedBlockingQueue 中的元素。
**返回值:**该方法不返回任何内容。
**异常:**该方法抛出以下异常:

*   **中断异常**–等待队列可用时发生中断
*   **空指针异常**–如果传递给方法的元素为空

**注**:**blocking Queue**的 **put()** 方法继承了 Java 中的 **Queue** 类。
下面的程序说明了阻塞队列类的 put(E e)方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate put(E e)
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

        // Add element using put() method
        BQ.put("Karan");
        BQ.put("Suraj");
        BQ.put("Harsh");
        BQ.put("Rahul");

        // print elements of queue
        System.out.println("Items in Queue are " + BQ);
    }
}
```

**Output:** 

```java
Items in Queue are [Karan, Suraj, Harsh, Rahul]
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate put()
// method of BlockingQueue

import java.util.Iterator;
import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;
public class GFG {

    public void PutDemo() throws InterruptedException
    {
        // define capacity of BlockingQueue
        int capacityOfQueue = 5;

        // create object of BlockingQueue
        BlockingQueue<Employee> BQ
            = new LinkedBlockingQueue<Employee>(capacityOfQueue);

        // Add element to BlockingQueue
        Employee emp1 = new Employee("Ranjeet", "Tester", "29000", 27);
        Employee emp2 = new Employee("Sanjeet", "Manager", "98000", 34);
        Employee emp3 = new Employee("Karan", "Analyst", "44000", 30);

        // Add Employee Objects to BQ
        // Using put(E e)
        BQ.put(emp1);
        BQ.put(emp2);
        BQ.put(emp3);

        System.out.println("Details of Employees:");
        // print details of BQ
        Iterator itr = BQ.iterator();
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

**程序 3:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate put(E e)
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

        // try to put null value in put method
        try {
            BQ.put(null);
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

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blockingqueue . html # put(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingQueue.html#put(E))