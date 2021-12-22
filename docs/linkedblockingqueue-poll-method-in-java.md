# Java 中的 LinkedBlockingQueue poll()方法

> 原文:[https://www . geeksforgeeks . org/linkedblockingqueue-poll-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingqueue-poll-method-in-java/)

LinkedBlockingQueue 中有两种轮询()方法。

### 民意测验()

**LinkedBlockingQueue** 的 **poll()** 方法通过从队列中移除该元素来返回 LinkedBlockingQueue 的头部。可以说，这个方法从这个 LinkedBlockingQueue 的头部检索并移除元素。如果队列为空，则轮询方法返回 null。

**语法:**

```
public E poll()
```

**返回值:**这个方法从这个 LinkedBlockingQueue 的头中检索并移除元素。如果队列为空，则返回 null。

下面的程序说明了 LinkedBlockingQueue 类的 poll()方法:

**程序 1:** 使用 poll()方法从 LinkedBlockingQueue 中移除元素，其中 LinkedBlockingQueue 包含名称列表。

```
// Java Program Demonstrate poll()
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
public class GFG {

    public static void main(String[] args)
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 4;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<String> linkedQueue
            = new LinkedBlockingQueue<String>(capacityOfQueue);

        // Add element to LinkedBlockingQueue
        linkedQueue.add("Ravi");
        linkedQueue.add("Suraj");
        linkedQueue.add("Harsh");
        linkedQueue.add("Sayan");

        // print elements of queue
        System.out.println("Items in Queue are " + linkedQueue);

        // we want to remove two elements from queue from head
        // Applying poll() method on queue to remove element
        String removedItem1 = linkedQueue.poll();

        // print removedItem and queue
        System.out.println("Removed Item is " + removedItem1);

        // print elements of queue after removing first item
        System.out.println("Remaining Items in Queue are "
                           + linkedQueue);

        // Applying poll() method on queue to remove another element
        String removedItem2 = linkedQueue.poll();

        // print removedItem and queue
        System.out.println("Removed Item is " + removedItem2);

        // print elements of queue after removing first item
        System.out.println("Remaining Items in Queue are " + linkedQueue);
    }
}
```

**Output:**

```
Items in Queue are [Ravi, Suraj, Harsh, Sayan]

Removed Item is Ravi
Remaining Items in Queue are [Suraj, Harsh, Sayan]

Removed Item is Suraj
Remaining Items in Queue are [Harsh, Sayan]

```

**程序 2:** 从包含员工列表的链接锁定队列中删除元素，如果队列为空，则打印空。

```
// Java Program Demonstrate poll()
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
public class GFG {

    public void pollingMethod()
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 5;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Employee> linkedQueue
            = new LinkedBlockingQueue<Employee>(capacityOfQueue);

        // Add element to LinkedBlockingQueue
        Employee emp1 = new Employee("Ravi", "Tester", "39000");
        Employee emp2 = new Employee("Sanjeet", "Manager", "98000");

        // Add Employee Objects to linkedQueue
        linkedQueue.add(emp1);
        linkedQueue.add(emp2);

        // remove elements from the queue
        // and follow this process again and again
        // until the queue becomes empty
        while (linkedQueue.size() != 0) {

            // Remove Employee item from LinkedBlockingQueue
            Employee removedEmp = linkedQueue.poll();

            // print removedItem
            System.out.println("Removed Item is :");
            System.out.println("Employee Name - " + removedEmp.name);
            System.out.println("Employee Position - " + removedEmp.position);
            System.out.println("Employee Salary - " + removedEmp.salary);

            // find size  of linkedQueue
            int size = linkedQueue.size();

            // print remaining capacity value
            System.out.println("\nSize of list :" + size + "\n");
        }

        // Now size of Queue is Zero
        // Now try to Poll more items
        // Remove Employee item from LinkedBlockingQueue
        Employee removedEmp = linkedQueue.poll();

        // print removedItem
        // size is zero so removedItem is null
        System.out.println("Removed Item is : " + removedEmp);
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
        gfg.pollingMethod();
    }
}
```

**Output:**

```
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

Removed Item is : null

```

### 轮询(长超时，时间单位单位)

**链接锁定队列**的**轮询(长超时，时间单位单位)**方法通过从队列中移除该元素来返回链接锁定队列的头部。可以说，这个方法从这个 LinkedBlockingQueue 的头部检索并移除元素。如果队列为空，那么 poll()方法将等待指定的时间，直到某个元素变为可用。

**语法:**

```
public E poll(long timeout, TimeUnit unit) throws 
```

**参数:**该方法取两个强制参数:

*   **超时**–等待时间，单位为单位。
*   **单位**–超时参数的时间单位。

**返回值:**这个方法从这个 LinkedBlockingQueue 的头中检索并移除元素，如果在元素可用之前指定的等待时间已经过去，则返回 null。

**异常**如果方法在等待元素可用时中断，此方法将引发**中断异常**。

下面的程序说明了 LinkedBlockingQueue 类的轮询(长超时，时间单位单位)方法:

**程序 1:** 使用 poll()方法从 LinkedBlockingQueue 中移除元素，其中 LinkedBlockingQueue 包含名称列表。

```
// Java program to demonstrate
// poll(long timeout, TimeUnit unit)
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.TimeUnit;

public class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 4;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<String> linkedQueue
            = new LinkedBlockingQueue<String>(capacityOfQueue);

        // Add element to LinkedBlockingQueue
        linkedQueue.add("Ravi");
        linkedQueue.add("Suraj");
        linkedQueue.add("Harsh");

        // print elements of queue
        System.out.println("Items in Queue are " + linkedQueue);

        // Try to poll elements from linkedQueue
        // using poll(long timeout, TimeUnit unit) method
        System.out.println("Removing item From head: "
                           + linkedQueue.poll(5, TimeUnit.SECONDS));

        // print queue details
        System.out.println("Now Queue Contains" + linkedQueue);

        // using poll(long timeout, TimeUnit unit) method
        System.out.println("Removing item From head: "
                           + linkedQueue.poll(5, TimeUnit.SECONDS));

        // print queue details
        System.out.println("Now Queue Contains" + linkedQueue);

        // using poll(long timeout, TimeUnit unit) method
        System.out.println("Removing item From head: "
                           + linkedQueue.poll(5, TimeUnit.SECONDS));

        // print queue details
        System.out.println("Now Queue Contains" + linkedQueue);

        // using poll(long timeout, TimeUnit unit) method
        System.out.println("Removing item From head: "
                           + linkedQueue.poll(5, TimeUnit.SECONDS));
        // print queue details
        System.out.println("Now Queue Contains" + linkedQueue);
    }
}
```

**Output:**

```
Items in Queue are [Ravi, Suraj, Harsh]

Removing item From head: Ravi
Now Queue Contains[Suraj, Harsh]

Removing item From head: Suraj
Now Queue Contains[Harsh]

Removing item From head: Harsh
Now Queue Contains[]

Removing item From head: null
Now Queue Contains[]

```

**参考:**

*   [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue . html # poll–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html#poll--`)
*   [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue . html # poll-long-Java . util . concurrent . time unit-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html#poll-long-java.util.concurrent.TimeUnit-)