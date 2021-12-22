# Java 中 LinkedBlockingQueue size()方法

> 原文:[https://www . geeksforgeeks . org/linkedblockingqueue-size-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingqueue-size-method-in-java/)

LinkedBlockingQueue 的 **size()** 方法返回 LinkedBlockingQueue 包含的元素个数。当队列为空队列时，size()返回 0，当队列已满时，size()返回队列的容量。

**语法:**

```java
public int size()
```

**返回值:**该方法返回链接锁定队列中该时刻的元素数量。返回类型是 int。

下面的程序说明了 LinkedBlockingQueue 类的 size()方法:

**程序 1:** 在 LinkedBlockingQueue 上执行添加和删除操作，每次操作后使用 size()

```java
// Java Program Demonstrate size()
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

        // get size of queue using size() method
        int size = linkedQueue.size();

        // print elements of queue and size of queue
        System.out.println("Items in Queue are " + linkedQueue);
        System.out.println("Size of Queue is " + size);

        // add more elements
        linkedQueue.put("Harsh");
        linkedQueue.put("Rahul");

        // get size of queue using size() method
        size = linkedQueue.size();

        // print elements of queue and size of queue
        System.out.println("Items in Queue are " + linkedQueue);
        System.out.println("Size of Queue is " + size);

        // try to remove element fom Queue
        boolean try1 = linkedQueue.remove("Karan");
        System.out.println("String name Karan is removed :"
                           + try1);

        // get size of queue using size() method
        size = linkedQueue.size();

        // print elements of queue and size of queue
        System.out.println("Items in Queue are " + linkedQueue);
        System.out.println("Size of Queue is " + size);
    }
}
```

**打印队列大小输出:**

```java
Items in Queue are [Karan, Suraj]
Size of Queue is 2

Items in Queue are [Karan, Suraj, Harsh, Rahul]
Size of Queue is 4

String name Karan is removed :true
Items in Queue are [Suraj, Harsh, Rahul]
Size of Queue is 3

```

**程序 2:** 对包含 Employee 对象的 LinkedBlockingQueue 执行添加和删除操作，每次操作后使用 size()

```java
// Java Program Demonstrate size()
// method of LinkedBlockingQueue

import java.util.Iterator;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    public void sizeDemo() throws InterruptedException
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 5;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Employee> linkedQueue
            = new LinkedBlockingQueue<Employee>(capacityOfQueue);

        // get size of queue using size() method
        int size = linkedQueue.size();
        System.out.println("Size of Queue " + size);

        // Add element to LinkedBlockingQueue
        Employee emp1 = new Employee("Ranjeet", "Tester", "29000", 27);
        Employee emp2 = new Employee("Sanjeet", "Manager", "98000", 34);
        Employee emp3 = new Employee("Karan", "Analyst", "44000", 30);

        // Add Employee Objects to linkedQueue
        // Using put(E e)
        linkedQueue.put(emp1);
        linkedQueue.put(emp2);
        linkedQueue.put(emp3);

        // print details of linkedQueue
        System.out.println("\nAfter Adding some Elements queue has");
        Iterator itr = linkedQueue.iterator();
        while (itr.hasNext())
            System.out.println(itr.next());

        // get size of queue using size() method
        size = linkedQueue.size();
        System.out.println("\nAfter Adding Size of Queue " + size);

        // remove employee2 name Sanjeet and Ranjeet from linkedQueue
        linkedQueue.remove(emp2);
        linkedQueue.remove(emp1);

        // print details of linkedQueue
        System.out.println("\nAfter removing Some Elements");
        itr = linkedQueue.iterator();
        while (itr.hasNext())
            System.out.println(itr.next());

        // get size of queue using size() method
        size = linkedQueue.size();
        System.out.println("\nAfter removing size of Queue " + size);
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
                + position + ", salary=" + salary + ", Age=" + Age + "]";
        }
    }

    // Main Method
    public static void main(String[] args)
    {
        GFG gfg = new GFG();
        try {
            gfg.sizeDemo();
        }
        catch (InterruptedException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        }
    }
}
```

**输出:**

```java
Size of Queue 0

After Adding some Elements queue has
Employee [name=Ranjeet, position=Tester, salary=29000, Age=27]
Employee [name=Sanjeet, position=Manager, salary=98000, Age=34]
Employee [name=Karan, position=Analyst, salary=44000, Age=30]

After Adding Size of Queue 3

After removing Some Elements
Employee [name=Karan, position=Analyst, salary=44000, Age=30]

After removing size of Queue 1

```

打印队列的大小

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue . html # size–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html#size--)